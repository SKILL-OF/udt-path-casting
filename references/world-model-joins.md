# World-model joins

Use typed `AS` segments to expose an information matrix through filesystem
traversal when agents should not require a database client.

## Relationship shape

A qualified casting joins dimensions observed together:

```text
___/AS/NETWORK/192.168.0.0_24/AS/MAC/F4-F5-D8-CB-CA-3A/AS/HOST/AURORA/AS/IP/192.168.0.35/_
```

Choose and document one canonical dimension order for qualified records. The
order is a traversal convention, not a claim that one dimension owns another.
Alternate entry points should act as indexes into canonical records rather
than duplicating the same relationship in every possible ordering:

```text
___/AS/MAC/F4-F5-D8-CB-CA-3A/_
___/AS/HOST/AURORA/_
___/AS/IP/192.168.0.35/_
___/AS/NETWORK/192.168.0.0_24/AS/IP/.35/_
```

Treat these shallow forms as secondary indexes. A pointer may resolve to one
current casting, several candidates, or a small manifest describing ambiguity.
When several current candidates remain, keep the candidate manifest; never
select one arbitrarily.

Omit dimensions that were not observed. For example, use
`AS/MAC/<value>/AS/IP/<value>` when no hostname is known; do not manufacture
`HOST/UNKNOWN` as though it were an observation.

## Time and evidence

Do not overwrite history merely because a new observation is newer. If Aurora
moves from `.35` to `.42`, retain both relationships and mark their observation
windows. If `.35` is later reused, create a new relationship rather than
merging entities by address.

Useful leaf metadata:

```yaml
first_seen: 2026-08-19T18:40:00-07:00
last_seen: 2026-08-19T18:49:00-07:00
status: current
confidence: observed
sources: [arp, router-dhcp]
```

Keep observation, inference, recruitment status, and authority separate. A
MAC/host/IP correlation does not by itself establish a physical device, owner,
or BHARTII relationship.

## Deterministic values

- Normalize MAC addresses to uppercase hyphenated hexadecimal.
- Normalize hostnames consistently while retaining observed spelling in
  metadata when it matters.
- Keep full IPv4 addresses in canonical targets; use `.35` only inside an
  explicit network scope.
- Encode CIDR `/` as `_`, for example `192.168.0.0_24`.
- Encode IPv6 reversibly because `:` is illegal in Windows filenames. Document
  the encoding next to the index; do not rely on an undocumented lossy slug.
- Reject or escape Windows reserved names and trailing spaces or periods.

## Pointer portability

Filesystem symlinks are convenient but not guaranteed. Windows may require
Developer Mode or elevation, repositories may not preserve links as expected,
and remote filesystems may expose them differently.

Use the best supported representation without changing semantics:

1. relative symbolic link;
2. junction when it safely addresses a directory on the same Windows volume;
3. small pointer file containing a relative target;
4. index manifest containing one or more candidate targets and confidence.

Never replace an existing pointer silently. Reconcile it against evidence and
preserve ambiguity when more than one target remains plausible.

## Behavioral check

Given the same MAC and hostname at `.35` at T1 and `.42` at T2, followed by a
different host reusing `.35`, a correct casting:

- retains all time-valid relationships;
- points current MAC/HOST indexes toward `.42` when evidence supports it;
- does not merge the later `.35` host into the earlier one;
- works without symlink support;
- does not label either entity a `bhartii-device` without separate evidence.
