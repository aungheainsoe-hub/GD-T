# 1. Fundamentals

## The 14 geometric characteristics

| Category | Characteristics | Datum needed? |
|---|---|---|
| **Form** | Straightness, Flatness, Circularity, Cylindricity | No |
| **Orientation** | Perpendicularity, Parallelism, Angularity | Yes |
| **Location** | Position, Concentricity, Symmetry | Yes |
| **Profile** | Profile of a line, Profile of a surface | Optional |
| **Runout** | Circular runout, Total runout | Yes |
<img width="897" height="601" alt="table-gd" src="https://github.com/user-attachments/assets/3c0cdd80-ba93-4f9d-bea1-269d3491bfbc" />

## Form vs profile

This is the distinction that confuses people most, so it's worth being precise.

**Form** controls a feature against its own ideal shape — flat, straight, round,
cylindrical — and never uses a datum, because it says nothing about where the surface
sits or which way it points.

**Profile** controls a surface against a *defined true contour* (set by basic
dimensions). It may reference datums, and when it does, it also locks orientation and
location. Profile is the general-purpose tool; the form symbols are special-case
shortcuts. Flatness, for instance, is essentially "profile of a flat surface with no
datum."

The rule of thumb: simple shape, shape only → form. Any contour, or you also need to
control where it sits → profile.

![Form vs profile tolerance zones](images/form-vs-profile.svg)

## Material condition modifiers

| Modifier | Meaning | Effect |
|---|---|---|
| **MMC** Ⓜ | Maximum Material Condition (largest pin / smallest hole) | Grants **bonus tolerance** as the feature departs from MMC |
| **LMC** Ⓛ | Least Material Condition | Protects minimum wall / edge distance |
| **RFS** | Regardless of Feature Size (default) | No bonus; tolerance is fixed at the stated value |

**Bonus tolerance** is the practical payoff of MMC. As a hole is drilled larger than
its smallest allowed size (its MMC), the position tolerance effectively grows, because
a bolt will still pass and the parts still assemble. That extra tolerance is free yield
for manufacturing.

## The two rules

**Rule #1 — the envelope principle ("size controls form").** A feature of size must
have perfect form at MMC; as it departs from MMC toward LMC, it earns that much form
tolerance for free. This is why you only add a separate flatness or straightness
callout when the function needs form *tighter* than the size limits already guarantee.

![Rule 1 envelope principle](images/rule1-envelope.svg)

**Rule #2 — RFS by default.** Every geometric tolerance applies regardless of feature
size unless Ⓜ or Ⓛ is stated. Bonus tolerance only exists when you ask for it with a
modifier.

*(Plus the screw-thread convention: tolerances and datums on threaded features default
to the pitch diameter unless MAJOR DIA or MINOR DIA is noted.)*
