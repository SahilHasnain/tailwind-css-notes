## 🎯 Lesson 11: **Shadows, Depth & Elevation – Realism aur Layered Feel ka Secret 🪟**

### 🔑 Why It Matters:

Flat design boring lagta hai. Shadows aur elevation se design mein aata hai:

* Layered feel (depth)
* Focus (kya cheez important hai)
* Real-world inspired look (modern UI ka essence)

---

## ☁️ Tailwind Shadow Utilities:

| Class         | Description         |
| ------------- | ------------------- |
| `shadow-sm`   | Light shadow        |
| `shadow`      | Default soft shadow |
| `shadow-md`   | Medium elevation    |
| `shadow-lg`   | Strong elevation    |
| `shadow-xl`   | Prominent shadow    |
| `shadow-2xl`  | Deepest depth       |
| `shadow-none` | No shadow           |

---

## ✨ Tips for Using Shadows:

1. **Use light shadow for cards**: `shadow` ya `shadow-md`
2. **Buttons ko thoda elevate karna**: `shadow-md` + `hover:shadow-lg`
3. **Modals, overlays:** `shadow-xl` or `shadow-2xl`
4. **Avoid overuse** — ek screen pe sirf selected elements ko shadow do

---

## 🛠️ Bonus Utility:

You can use `transition` with shadow for smooth hover effects:

```html
<button class="bg-white px-6 py-3 rounded-lg shadow transition-shadow hover:shadow-lg">
  Hover Me
</button>
```

---

### ✅ Assignment:

1. Ek card bana jisme:

   * `shadow-md` by default
   * `hover:shadow-lg` for elevation effect
   * Inner content well-padded and rounded
2. Ek CTA button bana with:

   * Base shadow
   * `hover:` effect for 3D feel

---

### Assignment Solution:
```html
<section class="flex min-h-screen items-center justify-center bg-gray-50 px-4 py-20">
  <div class="max-w-md w-full rounded-xl bg-white p-6 shadow-md transition hover:shadow-lg">
    <h1 class="mb-4 text-2xl font-bold text-gray-900">Next-Gen UI Design</h1>
    <p class="mb-6 leading-relaxed text-gray-600">Shadow se aati hai depth. Aur depth se aata hai visual hierarchy. Yeh hi hota hai professional design ka secret.</p>
    <button class="rounded-lg bg-purple-600 px-6 py-3 text-white shadow hover:bg-purple-700 hover:shadow-lg transition">Elevate Your UI</button>
  </div>
</section>
```
---
