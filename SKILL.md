---
name: udt-path-casting
description: Resolve UPN/UDT-style filesystem casts for private, shared, and world-edge agent spaces, including evidence-backed MAC, hostname, IP, and network relationship paths. Use before interpreting or creating agent-owned casting paths; do not use for ordinary filesystem organization.
---

# UDT Path Casting

Use this skill to determine what a path means before acting in a multi-agent
workspace. The path is an attribution contract, not decorative naming.

## Core grammar

- `_` is an **ungeon**: a single-agent zone.
- `__` is a **dungeon**: a group-capable container where multiple agents may
  interact.
- `___` is a **thungeon**: an edge where a local cast meets another authority,
  machine, network, person, or world model. It may carry escalation, but does
  not imply elevated OS privilege.
- `AS` introduces an as-cast identity or role.
- `__/AS/<shared-identity>/AS/<personal-identity>/_` is a valid solo agent
  home: one actor projecting into a shared identity space while retaining a
  private write zone.

## Typed world-model joins

Under a thungeon, `AS/<TYPE>/<VALUE>` may cast an observed dimension such as
`NETWORK`, `MAC`, `HOST`, or `IP`. Repeated `AS` segments materialize an
evidence-backed relationship:

```text
___/AS/NETWORK/192.168.0.0_24/AS/MAC/F4-F5-D8-CB-CA-3A/AS/HOST/AURORA/AS/IP/192.168.0.35/_
```

The leaf is a casting of that observed combination, not proof of a permanent
device identity. MAC addresses, hostnames, and IP addresses are mutable,
reusable, and potentially ambiguous. Permit many-to-many relationships and
preserve conflicting candidates.

Short paths such as `___/AS/HOST/AURORA/_` and
`___/AS/IP/192.168.0.35/_` are indexes or pointers to qualified castings, not
independent identity records. Scope shortened IP forms such as `.35` beneath a
network cast. Preserve old relationships when an address or hostname changes.

An observed entity is not automatically a `bhartii-device`; recruitment or
recruitability is a separate relationship supplied by evidence or authority.

For normalization, history, portable pointer strategies, and Windows-safe
value encoding, read
[references/world-model-joins.md](references/world-model-joins.md).

## Before a filesystem action

1. Parse every underscore and `AS` segment from left to right.
2. Identify the shared/group identity and the personal actor separately.
3. Resolve the final `_` or `__` component: final `_` means personal work;
   final `__` means group work.
4. Check the local cast, repository remote, branch, and durable identity
   record before writing.
5. Attribute the mutation to the personal identity, even when the enclosing
   dungeon is shared.
6. If the path is ambiguous, stop at read-only inspection and report the
   competing parses.
7. For world-model joins, record source, confidence, first/last observation,
   and current/historical status outside the path or in leaf metadata.

## Boundaries

Do not treat access, privacy, repository naming, or a shared dungeon as proof
of ownership. A private repo may be a shared resource, a template, another
agent's individual record, or unresolved. Keep the GitHub actor, agent card,
harness session, shared identity, personal identity, and filesystem custodian
as separate fields.

For detailed grammar examples and historical correlations, read
[references/udt-upn-correlations.md](references/udt-upn-correlations.md).
