# UPN/UDT correlations

This reference records the strongest available correlations, not a claim that
the historical public repositories expose a complete UPN specification.

## Path examples

```text
_/AS/<identity>/_
```

One agent's private ungeon.

```text
___/AS/<shared-identity>/AS/<personal-identity>/_
```

A personal actor projecting into a shared identity from the supernal
THUNGEON. The final `_` is the actor's private home; a `__` below the
THUNGEON is the group-capable context.

```text
___/AS/<shared-identity>/__
```

Collective work in a shared dungeon beneath the supernal THUNGEON. Use only
when group state, shared goals, or multi-agent exploration is intended.

```text
___/AS/<shared-identity>/AS/<personal-identity>/__
```

An individual actor's group-work surface inside a shared identity and beneath
the supernal THUNGEON. The final component is collective, so mutations need an
explicit group-work attribution.

The THUNGEON is `___` and is supernal to all `__` and `_` spaces. Do not treat
it as a synonym for a dungeon: a dungeon is a group work surface, while the
THUNGEON is the higher-order field containing the dungeon/ungeon hierarchy.

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
`___/AS/<shared-identity>/AS/<personal-identity>/_` disambiguates which actor of
a group writes to disk, while placing the actor below the supernal THUNGEON.
The skill adopts this as the canonical solo projection pattern. The
neighboring `📎10♠️` office surface remains a separate identity; its shared
relationship belongs in a dungeon beneath the THUNGEON, while each actor
retains an ungeon for attributable work.
