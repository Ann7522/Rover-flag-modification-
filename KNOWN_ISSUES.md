# Known Issues & Limitations

## 1. Low Natural Frequency (5.7 Hz)

**Problem:**  
With flag height 770 mm, the natural frequency is 5.7 Hz, which falls within the rover's vibration spectrum (5–30 Hz).

**Without Compensator:**  
- Resonance amplification: ×10  
- Peak stress: 54 MPa → exceeds PETG yield strength (50 MPa) → failure

**With Compensator (installed):**  
- Resonance amplification reduced to ×2.2  
- Peak stress: 11.9 MPa → safe (margin 4.2×)

**Status:** ✅ RESOLVED by Compensator

---

## 2. Limited Wind Resistance

**Problem:**  
At 770 mm height, wind load creates high bending stress.

| Wind speed | Stress | Status |
|------------|--------|--------|
| 7 m/s | 30 MPa | ✅ Safe |
| 8 m/s | 35 MPa | ⚠️ Margin 1.4× |
| 10 m/s | 55 MPa | ❌ Failure |

**Recommendation:**  
- Use only in wind <7 m/s  
- For outdoor use, reduce height to 470 mm or increase diameter to 25 mm

**Status:** ⚠️ OPEN — design limitation

---

## 3. Plastic Thread Durability

**Problem:**  
M3 threads directly in PETG wear after 5–10 assembly cycles.

**Mitigation:**  
- Use heat-set brass inserts  
- Or use nuts on the back side (accessible when rover is disassembled)

**Status:** ⚠️ Mitigated — acceptable for concept

---

## 4. Compensator Material

**Problem:**  
If printed in PETG, the compensator provides less damping than TPU.

**Recommendation:**  
Print Compensator in **TPU (Shore 95A)** for maximum vibration isolation.

**Status:** ⚠️ Recommendation only — PETG works but less effective

---

## Summary Table

| Issue | Severity | Status |
|-------|----------|--------|
| Resonance 5.7 Hz | High | ✅ Resolved (Compensator) |
| Wind >7 m/s | Medium | ⚠️ Open (design limit) |
| Thread wear | Low | ⚠️ Mitigated |
| Compensator material | Low | ℹ️ Recommendation |
