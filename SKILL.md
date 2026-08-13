---
name: udt-path-casting
description: Resolve UPN/UDT-style filesystem casts for shared dungeons, individual ungeons, and personal projections before reading or writing agent-owned files.
---

# UDT Path Casting

Use this skill to determine what a path means before acting in a multi-agent
workspace. The path is an attribution contract, not decorative naming.

## Core grammar

- `_` is an **ungeon**: a single-agent zone.
- `__` is a **dungeon**: a group-capable container where multiple agents may
  interact.
- `thungeon` is a dungeon whose purpose is explicitly collective exploration,
  status, or goals; do not infer that purpose from underscores alone.
- `AS` introduces an as-cast identity or role.
- `__/AS/<shared-identity>/AS/<personal-identity>/_` is a valid solo agent
  home: one actor projecting into a shared identity space while retaining a
  private write zone.

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

## Boundaries

Do not treat access, privacy, repository naming, or a shared dungeon as proof
of ownership. A private repo may be a shared resource, a template, another
agent's individual record, or unresolved. Keep the GitHub actor, agent card,
harness session, shared identity, personal identity, and filesystem custodian
as separate fields.

For detailed grammar examples and historical correlations, read
[references/udt-upn-correlations.md](references/udt-upn-correlations.md).
