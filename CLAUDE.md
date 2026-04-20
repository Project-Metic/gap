# CLAUDE.md — gap

Mirror / fork of gap-system/gap (Groups, Algorithms, Programming — computational group
theory system). Used by Project-Metic for algebraic analysis of crystal symmetry groups,
lattice symmetries, and formal algebraic structures in the materials science pipeline.

**Treat this as read-only upstream code** unless a Metic-specific patch is required.

## Key Invariants

- **GAP algebra correctness is axiomatic.** Never modify core GAP algebraic routines.
  GAP group-theoretic results are used downstream in symmetry analysis — an incorrect
  result here propagates silently.
- **Never publish a modified fork.** Metic's fork is private.
- **GAP packages must be version-pinned.** The GAP package ecosystem (HAP, Crystcat, etc.)
  is version-sensitive. Do not update packages without verifying compatibility.

## Dev Commands

```bash
# Build GAP
./configure && make

# Run GAP interactively
gap

# Run tests
make testinstall
```

## Tech Stack

- GAP language, C (GAP kernel)

## Integration with Project-Metic

- Used for algebraic symmetry analysis of crystal structures (companion to spglib)
- GAP algebraic results may feed into formal proof obligations for crystallographic symmetry

## What NOT to Do

- Do not modify core GAP algebraic routines
- Do not update GAP packages without version compatibility check
- Do not publish to any public package registry
