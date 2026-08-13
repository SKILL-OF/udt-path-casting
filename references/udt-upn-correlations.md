# UPN/UDT correlations

This reference records the strongest available correlations, not a claim that
the historical public repositories expose a complete UPN specification.

## Path examples

```text
_/AS/<identity>/_
```

One agent's private ungeon.

```text
__/AS/<shared-identity>/AS/<personal-identity>/_
```

A personal actor writing into a shared identity's dungeon. The final `_` is
the actor's private home; the parent `__` is the group-capable context.

```text
__/AS/<shared-identity>/__
```

Collective work in the shared dungeon itself. Use only when group state,
shared goals, or multi-agent exploration is intended.

```text
__/AS/<shared-identity>/AS/<personal-identity>/__
```

An individual actor's group-work surface inside a shared identity. The final
component is collective, so mutations need an explicit group-work attribution.

## Historical correlations

- `GHORGS-OF/walrus-man` establishes semantic ghorg/repository casting and
  refers to an “ungeon path”, but does not define the full UPN/UDT grammar.
- `DashBOrg-of/dashborg-of` treats dungeon/ungeon context as part of the local
  stewardship snapshot, correlating path context with agent/workspace state.
- `AWG26/TASQS.AS.THE_AGENTIC_SEMVER_QUDDITY_SYSTEM` separates avatar, sidecar,
  reboot, and full identity layers. This supports separating shared identity,
  personal identity, and context-window lineage, but is not itself a path spec.
- `VGM9/session-tools` and `VGM9/reboot-count` provide structured session and
  reboot evidence. They support attribution of a filesystem write to a
  session/instance but do not define dungeon semantics.
- `wordgarden-dev/agentic-work-week` supplies the broader WordGarden practice
  of agent-scale time, handoff, and documentation; no public UPN/UDT source was
  found through the available GitHub API during this skill's first pass.

## Evidence posture

Record historical correlations as supporting evidence. Keep the current
UPN/UDT grammar explicit as a working contract until a canonical WordGarden
specification is found. Never silently upgrade an analogy into a standard.

## Case study

2026-08-13, `🔱9♦️`: the user's correction established that
`__/AS/<shared-identity>/AS/<personal-identity>/_` disambiguates which actor of
a group writes to disk. The skill adopts this as the canonical solo projection
pattern. The neighboring `📎10♠️` office surface remains a separate identity;
its shared relationship belongs in a dungeon, while each actor retains an
ungeon for attributable work.
