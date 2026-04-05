# Chapter 2: Lines and Planes in R³ — Summary

## Lines in R³

A line in space is determined by a **point** P₀(x₀, y₀, z₀) and a **direction vector** v = (v₁, v₂, v₃).

### Three equivalent forms

**Vector form:**
```
r₁ = r₀ + λv,   λ ∈ ℝ
```

**Parametric form:**
```
x = x₀ + λv₁
y = y₀ + λv₂
z = z₀ + λv₃
```

**Canonical form** (requires all vᵢ ≠ 0):
```
(x − x₀)/v₁ = (y − y₀)/v₂ = (z − z₀)/v₃ = λ
```

The representation is not unique — any point on the line can serve as the base point, and any nonzero scalar multiple of v gives the same line.

---

## Planes in R³

A plane is determined by a **point** R₀(x₀, y₀, z₀) and a **normal vector** n = (a, b, c) perpendicular to the plane.

### Three equivalent forms

**Vector form:**
```
⟨n, r − r₀⟩ = 0
```

**General form:**
```
ax + by + cz = d,   where d = ax₀ + by₀ + cz₀
```

**Vector parametric description:**
```
r₀ + λu + μv,   λ, μ ∈ ℝ
```
where u, v are two linearly independent vectors lying in the plane.

To convert parametric → general: find n = u × v (the cross product of the two direction vectors), then substitute the support point to get d.

Three noncollinear points A, B, C also determine a plane via:
```
|(x−x₀  y−y₀  z−z₀)|
|(x₁−x₀ y₁−y₀ z₁−z₀)| = 0
|(x₂−x₀ y₂−y₀ z₂−z₀)|
```

---

## 2.1 Intersections

### Two lines
Lines ℓ₁ = r₁ + λ₁v₁ and ℓ₂ = r₂ + λ₂v₂ intersect iff there exist λ₁, λ₂ such that:
```
r₁ + λ₁v₁ = r₂ + λ₂v₂
```
This gives a system of 3 equations; check consistency in all three coordinates.

### Line and plane
Substitute the parametric line ℓ = r₀ + λv into the plane equation ax + by + cz = d and solve for λ. Then substitute back to get the intersection point.
- If the equation has no solution → line is parallel to plane (no intersection).
- If all λ ∈ ℝ satisfy it → line lies in the plane.

### Two planes
Two non-parallel planes intersect in a **line**. Solve the system of two plane equations, express two unknowns in terms of the third (assign it parameter λ), and write the result in vector form.

---

## 2.2 Distances

### Point to line
Let R₁ be the point, ℓ = r₀ + λv the line:
```
Δ = |(r₁ − r₀) × v| / |v|
```

### Point to plane
Let R₁ be the point, Π a plane with normal n, and R₀ any point on Π:
```
Δ = |⟨r₁ − r₀, n⟩| / |n|
```

### Two parallel lines
Check parallelism: v₁ × v₂ = 0 (equivalently, v₁ and v₂ are linearly dependent).
Distance = distance from any point on ℓ₁ to ℓ₂ (use the point-to-line formula).

### Two skew lines
Lines that are not parallel and do not intersect. Formula:
```
Δ = |⟨v₁ × v₂, r₂ − r₁⟩| / |v₁ × v₂|
```

### Line and parallel plane
First verify parallelism: ⟨n, v⟩ = 0.
Distance = distance from any point on the line to the plane (use the point-to-plane formula).

### Two parallel planes
First verify: n₁ = α n₂ for some scalar α.
Distance = distance from any point on one plane to the other plane.

---

## 2.3 Angles

### Between two lines
The angle φ is always taken as **acute**:
```
cos φ = |⟨v₁, v₂⟩| / (|v₁| · |v₂|)
```

### Between a line and a plane
The angle φ is between the line and its projection onto the plane:
```
sin φ = |⟨v, n⟩| / (|v| · |n|)
```
where n is the normal to the plane. Equivalently: φ = 90° − β, where β is the angle between v and n.

### Between two planes
The angle equals the angle between the normal vectors:
```
cos φ = |⟨n₁, n₂⟩| / (|n₁| · |n₂|)
```
Two planes are **orthogonal** iff ⟨n₁, n₂⟩ = 0.
