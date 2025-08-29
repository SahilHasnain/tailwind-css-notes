# Grid System in Tailwind CSS

Grid layout Tailwind me ek 2-dimensional layout system hai jisme tum rows aur columns dono define kar sakte ho. Ye complex layouts banane ke liye Flexbox se bhi powerful hai.

## Basic Grid Setup

Grid ko activate karne ke liye:

```html
<div class="grid grid-cols-3 gap-4">
  <div class="bg-red-200">1</div>
  <div class="bg-green-200">2</div>
  <div class="bg-blue-200">3</div>
</div>
```

Is example me:
- `grid` container ko grid banata hai
- `grid-cols-3` 3 columns create karta hai
- `gap-4` har cell ke beech 1rem ka space deta hai

## Grid Columns

Tailwind pre-defined grid columns ki range deta hai:

| Class | Meaning |
|-------|---------|
| `grid-cols-1` | 1 column |
| `grid-cols-2` | 2 columns |
| `grid-cols-3` | 3 columns |
| `grid-cols-4` | 4 columns |
| `grid-cols-5` | 5 columns |
| `grid-cols-6` | 6 columns |
| `grid-cols-12` | 12 columns |
| `grid-cols-none` | No defined columns |

## Grid Rows

Rows ko explicitly define karne ke liye:

```html
<div class="grid grid-rows-3 grid-cols-2 gap-2">
  <div class="bg-red-300">A</div>
  <div class="bg-red-400">B</div>
  <div class="bg-red-500">C</div>
  <div class="bg-red-600">D</div>
  <div class="bg-red-700">E</div>
  <div class="bg-red-800">F</div>
</div>
```

## Row and Column Gap (Spacing)

Gap size control karne ke liye:

| Class | Effect |
|-------|--------|
| `gap-4` | All gaps 1rem |
| `gap-x-4` | Horizontal gaps only |
| `gap-y-4` | Vertical gaps only |

## Column Span (Columns Occupy Karna)

Ek grid item ko multiple columns occupy karane ke liye:

```html
<div class="grid grid-cols-3 gap-4">
  <div class="col-span-2 bg-purple-200">Span 2</div>
  <div class="bg-purple-300">1 col</div>
  <div class="bg-purple-400">1 col</div>
</div>
```

| Class | Effect |
|-------|--------|
| `col-span-1` | 1 column occupy (default) |
| `col-span-2` | 2 columns occupy |
| `col-span-3` | 3 columns occupy |
| ... | ... |
| `col-span-12` | 12 columns occupy |
| `col-span-full` | Full width span |

## Row Span (Rows Occupy Karna)

Ek grid item ko multiple rows occupy karane ke liye:

```html
<div class="grid grid-cols-3 grid-rows-3 gap-4">
  <div class="row-span-2 bg-indigo-400">Spans 2 rows</div>
  <div class="bg-indigo-300">Normal cell</div>
  <div class="bg-indigo-300">Normal cell</div>
</div>
```

| Class | Effect |
|-------|--------|
| `row-span-1` | 1 row occupy (default) |
| `row-span-2` | 2 rows occupy |
| `row-span-3` | 3 rows occupy |
| ... | ... |
| `row-span-6` | 6 rows occupy |
| `row-span-full` | Full height span |

## Start/End Positions

More precise control ke liye, tum specific positions bhi define kar sakte ho:

```html
<div class="grid grid-cols-6 gap-4">
  <div class="col-start-2 col-end-4 bg-purple-400">From 2 to 4</div>
  <div class="col-start-5 col-end-7 bg-purple-600">From 5 to 7</div>
</div>
```

| Class | Effect |
|-------|--------|
| `col-start-1` | Start at col line 1 |
| `col-end-4` | End at col line 4 |
| `row-start-2` | Start at row line 2 |
| `row-end-5` | End at row line 5 |

## Responsive Grid

Tailwind grid classes ko responsive bhi bana sakte ho:

```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
  <div class="bg-teal-100 p-4">Box 1</div>
  <div class="bg-teal-200 p-4">Box 2</div>
  <div class="bg-teal-300 p-4">Box 3</div>
  <div class="bg-teal-400 p-4">Box 4</div>
</div>
```

Is grid me:
- Small screens (mobile): 1 column
- Medium screens (tablet): 2 columns
- Large screens (desktop): 4 columns

## Complete Grid Example: Photo Gallery

```html
<div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 p-4">
  <div class="bg-white p-2 rounded shadow">
    <img src="https://via.placeholder.com/300x200" alt="Image" class="w-full h-48 object-cover rounded">
    <p class="mt-2 text-center">Photo 1</p>
  </div>
  <div class="bg-white p-2 rounded shadow">
    <img src="https://via.placeholder.com/300x200" alt="Image" class="w-full h-48 object-cover rounded">
    <p class="mt-2 text-center">Photo 2</p>
  </div>
  <div class="bg-white p-2 rounded shadow">
    <img src="https://via.placeholder.com/300x200" alt="Image" class="w-full h-48 object-cover rounded">
    <p class="mt-2 text-center">Photo 3</p>
  </div>
  <div class="bg-white p-2 rounded shadow">
    <img src="https://via.placeholder.com/300x200" alt="Image" class="w-full h-48 object-cover rounded">
    <p class="mt-2 text-center">Photo 4</p>
  </div>
  <div class="col-span-2 bg-white p-2 rounded shadow">
    <img src="https://via.placeholder.com/600x300" alt="Image" class="w-full h-48 object-cover rounded">
    <p class="mt-2 text-center">Featured Photo</p>
  </div>
</div>
```

## Practice Exercise

Ek responsive grid layout banao:
- Mobile pe 1 column
- Tablet pe 3 columns
- Desktop pe 4 columns
- Featured item ko 2 columns span karo 