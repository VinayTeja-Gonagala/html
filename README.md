# Interactive Bézier Curve with Spring Physics

This project implements an **interactive cubic Bézier curve** that behaves like a **springy rope**, responding smoothly to mouse or touch input. All Bézier math, tangent computation, and spring‑damping physics are implemented **manually**, without using external graphics or physics libraries.

---

##  Features

### **1. Cubic Bézier Curve Implementation**

The curve uses four control points:

* **P0** and **P3** — fixed endpoints
* **P1** and **P2** — dynamic points affected by physics and interaction

The curve is rendered by sampling the equation:

```
B(t) = (1−t)³P0 + 3(1−t)²tP1 + 3(1−t)t²P2 + t³P3
```

---

##  Tangent Visualization

Tangent vectors are computed using the derivative:

```
B'(t) = 3(1−t)²(P1−P0) + 6(1−t)t(P2−P1) + 3t²(P3−P2)
```

Short normalized tangent segments are drawn along the curve for better visualization.

---

##  Spring‑Damping Physics

P1 and P2 move according to a basic mass‑spring‑damper system:

```
acceleration = -k * (position - target) - damping * velocity
```

* **k** → spring constant
* **damping** → controls oscillations
* **target** → determined by user input

This creates smooth, rope‑like motion when interacting.

---

##  Interaction Model

### **Mouse / Touch Input**

* Moving the cursor changes the target positions of P1 and P2.
* Dragging directly over P1 or P2 allows manual repositioning.
* Touch screens fully supported.

### **Real‑time Rendering (60 FPS)**

Uses `requestAnimationFrame()` to achieve smooth visual updates.

---

##  Project Structure

This repository contains:

```
interactive_bezier.html   → Complete runnable web demo
README.md                 → Documentation
```

Everything runs in a browser — **no server or build step required**.

---

##  How to Run

1. Download or clone the repository.
2. Open `interactive_bezier.html` in any modern browser.
3. Move the mouse or drag the control points to interact.
4. Observe real-time curve deformation and physics simulation.

---

##  Assignment Rules Included

The interface displays the required assignment rules:

* No cheating
* No copying or plagiarism
* Proper citation when using external sources

---

##  Submission Requirements

You must submit:

* Source code (already included)
* README (this file)
* **30-second screen recording** demonstrating interaction

---

##  Technologies Used

* **HTML5 Canvas** — Rendering engine
* **Vanilla JavaScript** — Math, physics, input handling
* **No external libraries**

---

##  Notes

This implementation avoids any built-in animation, Bézier, or physics APIs. All logic is fully custom to satisfy typical assignment constraints.

If needed, an iOS (Swift + CoreMotion + CADisplayLink) version can also be provided.

---

##  Support

If you want additional features (sliders for spring constants, UI cleanup, Swift version, ZIP export), feel free to ask!
