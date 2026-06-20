# GD&T Portfolio

Geometric Dimensioning & Tolerancing (GD&T) defines the allowable variation in a
part's **form, orientation, location, and runout**, tied to **datums** — the
reference frame the part is measured from. It replaces vague +/- dimensions with
functional control of how a part actually fits and works.

This portfolio is built to show three things, in order of difficulty:
1. I can **read** a drawing and say what each callout means.
2. I can **reason** about why a callout is there, how it's inspected, and how it's made.
3. I can **critique** a drawing and spot when it's wrong.

## A note on standards
Two standards dominate: **ASME Y14.5** (US) and **ISO GPS** (Europe / international).
Most symbols are shared, but one key default flips. Under ASME, **Rule #1 (the
envelope principle)** applies by default, so size controls form. Under ISO, the
default is the **Principle of Independency**, and the envelope is invoked explicitly
with the Ⓔ modifier. I always confirm which standard a drawing uses before reading
any feature of size.

## How to read a feature control frame
Always left to right:

`[ characteristic | tolerance (Ø) (modifier) | primary datum | secondary | tertiary ]`

Example: `[ ⌖ | Ø0.2 Ⓜ | A | B | C ]` reads as *"position of this feature within a
0.2 mm diameter zone at maximum material condition, relative to datums A, B, and C."*

## Sections
1. [Fundamentals](01-fundamentals.md) — the 14 characteristics, modifiers, Rules 1 & 2
2. [Drawing interpretation](02-drawing-interpretation.md) — reading real callouts in plain English
3. [Applied reasoning](03-applied-reasoning.md) — function, inspection, and manufacturing impact
4. [Drawing critique](04-drawing-critique.md) — finding errors and ambiguity
5. [Worked calculations](05-worked-calculations.md) — bonus tolerance, virtual condition, datum shift
6. [Original parts](06-original-parts.md) — parts I toleranced and justified myself

---
*All drawings in this portfolio are original, generic examples created to demonstrate
the concepts. No proprietary or employer-owned files are reproduced.*
