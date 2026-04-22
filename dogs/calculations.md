# Engineering Calculations

## Material Properties (PETG)

| Property | Value |
|----------|-------|
| Young's modulus (E) | 2000 MPa |
| Yield strength (σ_y) | 50 MPa |
| Density | 1.27 g/cm³ |
| Damping ratio with Compensator | 0.15 |

---

## 1. Vibration Analysis (H = 770 mm)

### Natural Frequency
*I = π × d⁴ / 64 = 7.85×10⁻⁹ m⁴
*k = 3 × E × I / H³ = 103.2 N/m
*f₀ = (1/2π) × √(k/m) = 5.71 Hz

### With Compensator

| Frequency (Hz) | Input (g) | T | Output (g) | Stress (MPa) |
|----------------|-----------|----|------------|--------------|
| 5.7 (resonance) | 0.7 | 2.2 | 1.54 | 11.9 |
| 10 | 1.5 | 1.10 | 1.65 | 12.7 |
| 15 | 2.0 | 0.80 | 1.60 | 12.4 |
| 20 | 2.0 | 0.60 | 1.20 | 9.3 |

**Margin:** 50 / 11.9 = **4.2×** ✅

---

## 2. Wind Load Analysis (H = 770 mm, d = 20 mm)

| Wind (m/s) | F (N) | σ (MPa) | Deflection (mm) | Status |
|------------|-------|---------|-----------------|--------|
| 5 | 0.28 | 13.8 | 6.8 | ✅ Safe |
| 6 | 0.41 | 20.1 | 9.8 | ✅ Safe |
| 7 | 0.55 | 27.0 | 13.2 | ✅ Safe |
| 8 | 0.72 | 35.3 | 17.5 | ⚠️ Caution |
| 9 | 0.92 | 45.1 | 22.4 | ⚠️ Risk |
| 10 | 1.13 | 55.4 | 27.4 | ❌ Failure |

---

## 3. Summary Table

| Load case | Max stress (MPa) | Margin | Status |
|-----------|------------------|--------|--------|
| Vibration (with Compensator) | 11.9 | 4.2× | ✅ |
| Wind 7 m/s | 27.0 | 1.85× | ✅ |
| Wind 8 m/s | 35.3 | 1.42× | ⚠️ |
| Wind 9 m/s | 45.1 | 1.11× | ⚠️ |
| Wind 10 m/s | 55.4 | 0.90× | ❌ |

**Final verdict:**
- ✅ Vibration-safe with Compensator
- ⚠️ Wind-safe only up to 7 m/s
- ❌ Do not use in wind >9 m/s
