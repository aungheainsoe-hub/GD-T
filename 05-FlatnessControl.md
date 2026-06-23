## Flatness Control: Global vs. Unit-Area Tolerance

When a flatness tolerance is applied to a surface, it establishes a tolerance zone bounded by two parallel planes. Every point on the physical surface must lie entirely within this designated window. 
<p align="center">
<img width="1297" height="822" alt="image" src="https://github.com/user-attachments/assets/2c84d27d-2510-4876-9649-cf48895608b6" />
</p>

Providing a tight overall flatness control (such as $0.1\text{ mm}$ or less) across a significantly large block requires a massive amount of manufacturing time and cost. The machine shop is forced to ensure the entire global span sits perfectly flat, even though minor, gradual variations across long distances rarely affect assembly function.

---

### The Cost-Effective Solution: Per Unit Area Flatness

To optimize production costs while maintaining surface quality where it actually matters, engineers can use **Unit-Area Flatness**. This splits the constraint into two requirements inside a stacked feature control frame:
<p align="center">
  <img src="https://github.com/user-attachments/assets/0f3f00f7-ac4b-455d-81c2-8682c5f4bd9f" width="750" alt="Parallel Plane Flatness Tolerance Zone" />
</p>

1. **A Global Limit:** A larger, relaxed flatness tolerance across the entire surface.
2. **A Localized Unit Limit:** A tight flatness tolerance restricted to a small moving sample area (e.g., a $20\times20\text{ mm}$ square).

<p align="center">
  <img src="https://github.com/user-attachments/assets/a59086b1-2b5d-43b9-900f-4b108f768c46" width="750" alt="20X20 Unit Area Flatness Control" />
</p>

#### Manufacturing and Cost Benefits:
* **Allows Gradual Waves:** The machinist can let the large block gradually wave or bow over its long total length, which is easy and fast to machine.
* **Prevents Sharp Abrupt Steps:** The $20\times20\text{ mm}$ unit constraint ensures that there are no sharp peaks, sudden steps, or rough tool marks locally. This guarantees that small components mounting to any specific section of the block will still sit flush.
* **Reduces Scrap Rates:** By tolerancing the surface based on how it functions locally rather than demanding global perfection, production cycles speed up, tool wear decreases, and manufacturing costs drop significantly.


