# Fusion 360 Exercise 5: Geometric Constraints & Relations
## (Translated from Solid Edge ST9 Exercise)

### Objective
Create a technical sketch with geometric relationships, offsets, and symmetry. This appears to be a dual-chamber mechanical part (bearing housing or similar).

---

## Step 1: Setup & Initial Circles
- Create a new sketch on the XY plane
- Use **Circle** tool and draw from origin (0,0)
- Create 3 concentric circles with diameters:
  - Ø27mm
  - Ø40mm  
  - Ø45mm

---

## Step 2: Ellipse (Outer Profile)
- Use **Ellipse** tool (under Curves)
- Set center at origin (0,0)
- Draw ellipse: **120mm wide × 90mm high**
- Use **Constrain Horizontal** and **Constrain Vertical** to fix major/minor axes
- Dimension: When constraining ellipse, Fusion uses **semi-major and semi-minor** axes (so enter 60mm and 45mm for radii, OR use the actual dimensions in the constraint dialog)

---

## Step 3: Offset Ellipse (Create Inner Profile)
- Select the outer ellipse
- Use **Offset Edge** tool (or **Sketch Offset**)
- Offset **8mm inward**
- Click the ellipse curve to create the offset

---

## Step 4: Two Equal Side Circles
- Use **Circle** tool
- Draw from origin and move **right** (toward +X axis)
- A dashed construction line should appear vertically through origin
- Draw first circle on the right
- Draw second circle on the **left** (mirror position)
- Apply **Equal** constraint to both circles (they'll become the same size)

---

## Step 5: Dimension the Side Circles
- Circle diameter: **Ø14mm**
- Horizontal distance between circle centers: **92mm total**
  - This means **46mm from center to each circle center** (±46mm from origin)

**Constraint approach:**
- Constrain distance from origin to right circle center: 46mm
- Constrain distance from origin to left circle center: 46mm (or use **Symmetric** constraint)
- OR: Use **Equal** constraint + symmetric constraint for cleaner relations

---

## Step 6: Inner Circles on Side Circles
- On each of the two 14mm circles, draw new circles at their **centers**
- These circles: **Ø28mm each**
- Apply **Equal** constraint between the two 28mm circles
- They should be horizontally aligned with the 14mm circles

---

## Step 7: Horizontal Rectangle Through Center
- Use **Rectangle** tool (or draw with **Lines**)
- Draw centered on origin (0,0)
- Width: **14mm** (horizontal)
- Height: Variable (draw so it fits **between the two ellipses** — approximately 8-10mm total, or constrain to avoid the inner circles)
- Make sure corners don't extend beyond the ellipses

---

## Step 8: Trim Unnecessary Geometry
- Select the **Trim** tool
- Delete any overlapping or extra line segments
- Keep only the clean outer profile and internal features
- The final sketch should show clean geometry with no redundant lines

---

## Step 9: Add Filleted Corners
- Use **Fillet** tool on the sketch
- Select the **internal corners** (where the rectangle meets the ellipse)
- Fillet radius: **5mm**
- Apply to both top and bottom corners

---

## Final Constraints Summary

| Feature | Dimension | Constraint Type |
|---------|-----------|-----------------|
| Center circles | Ø27, Ø40, Ø45 | Concentric at origin |
| Outer ellipse | 120 × 90 mm | Centered at origin |
| Offset ellipse | 8mm inside | Offset constraint |
| Side circles (2×) | Ø14mm | Equal constraint |
| Side circle spacing | 92mm apart | Distance 46mm each side |
| Inner circles (2×) | Ø28mm | Equal constraint |
| Center rectangle | 14mm wide | Horizontal dimension |
| Filleted corners | R5mm | Fillet constraint |

---

## Key Differences: Fusion 360 vs Solid Edge

| Feature | Solid Edge | Fusion 360 |
|---------|-----------|-----------|
| Ellipse | Ellipse by Center Point | **Ellipse** (under Curves) — set in dialog or constrain after |
| Offset | Offset tool | **Offset Edge** or use **Sketch Offset** |
| Equal constraint | Equal (=) | **Equal** constraint (Sketch menu → Constrain) |
| Symmetric | Symmetric | **Symmetric** constraint |
| Fillet | Fillet | **Fillet** (Sketch toolbar or Sketch menu) |
| Trim | Trim | **Trim** (Sketch toolbar) |

---

## Export & Save
- When complete, click **Finish Sketch**
- Save as `.f3d` (Fusion native) or export as `.dxf` / `.step` if needed
- To create a 3D part, use **Pad** tool to extrude the sketch

---

## Tips
✓ Use **Fully Constrained** state (all geometry should be blue, not white/gray)  
✓ Apply constraints **progressively** — don't dimension everything at once  
✓ Use **Construction geometry** (toggle with `G`) for helper lines/circles  
✓ Check **Properties panel** to see all active constraints  
✓ Use **Undo** (Ctrl+Z) liberally if a constraint conflicts  

