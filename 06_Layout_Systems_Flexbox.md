# Layout System in Tailwind CSS: Flexbox

Flexbox Tailwind me ek powerful layout utility hai jo elements ko rows ya columns me organize karne ke liye use hota hai. Ye responsive layouts banane ke liye bahut useful hai.

## Container ko Flex banana

Tailwind me flexbox ko activate karne ke liye `flex` class use karte hain:

```html
<div class="flex">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

By default, ye items ko horizontally ek row me place karta hai.

## Direction Control (Flex Direction)

Flex container ki direction control karne ke liye:

| Class | Description |
|-------|-------------|
| `flex-row` | Horizontal direction (default) |
| `flex-col` | Vertical direction |
| `flex-row-reverse` | Reverse horizontal |
| `flex-col-reverse` | Reverse vertical |

**Example:**
```html
<div class="flex flex-col">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```

## Main Axis Alignment (Justify Content)

Items ko main axis par align karne ke liye (horizontally in row, vertically in column):

| Class | Kaam |
|-------|------|
| `justify-start` | Start me le aata hai (left ya top) |
| `justify-center` | Center karta hai horizontally |
| `justify-end` | End me le jata hai (right ya bottom) |
| `justify-between` | Items ke beech space daal deta hai |
| `justify-around` | Items ke around equal space |
| `justify-evenly` | Perfectly even spacing |

**Example:**
```html
<div class="flex justify-between items-center">
  <div>Left</div>
  <div>Right</div>
</div>
```

## Cross Axis Alignment (Items Alignment)

Items ko cross axis par align karne ke liye (vertically in row, horizontally in column):

| Class | Effect |
|-------|--------|
| `items-start` | Start se align |
| `items-center` | Vertically center karta hai |
| `items-end` | Bottom me le aata hai |
| `items-stretch` | Full height stretch (default) |
| `items-baseline` | Text baselines align |

**Example:**
```html
<div class="flex items-center h-20">
  <div>Centered vertically</div>
</div>
```

## Gap Between Items

Items ke beech me space add karne ke liye:

```html
<div class="flex gap-4">
  <div class="bg-blue-300 p-4">1</div>
  <div class="bg-blue-300 p-4">2</div>
  <div class="bg-blue-300 p-4">3</div>
</div>
```

- `gap-4` items ke beech 1rem ka gap create karta hai
- `gap-x-4` horizontal gap only
- `gap-y-4` vertical gap only

## Wrapping Flex Items

Flex items ko wrap karne ke liye, jisse overflow hone par next line me shift ho:

| Class | Effect |
|-------|--------|
| `flex-wrap` | Items wrap to next line |
| `flex-nowrap` | No wrapping (default) |
| `flex-wrap-reverse` | Reverse wrap order |

**Example:**
```html
<div class="flex flex-wrap gap-2">
  <div class="w-32 h-16 bg-blue-200">Box</div>
  <div class="w-32 h-16 bg-green-200">Box</div>
  <div class="w-32 h-16 bg-red-200">Box</div>
  <div class="w-32 h-16 bg-yellow-200">Box</div>
</div>
```

## Growing & Shrinking (Flex Items)

Individual flex items ko control karne ke liye:

| Class | Effect |
|-------|--------|
| `flex-1` | Flex grow 1, shrink 1, basis 0% |
| `flex-auto` | Flex grow 1, shrink 1, basis auto |
| `flex-initial` | Default (0 1 auto) |
| `flex-none` | No growing or shrinking |
| `grow` | Flex grow 1 |
| `shrink` | Flex shrink 1 |

## Complete Example: Navbar with Flexbox

```html
<nav class="flex justify-between items-center p-4 bg-gray-100">
  <h1 class="text-xl font-bold">Logo</h1>
  <div class="flex gap-6 text-gray-700">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </div>
</nav>
```

## Responsive Flex Example

```html
<div class="flex flex-col md:flex-row gap-4">
  <div class="bg-red-400 p-4 flex-1">Left</div>
  <div class="bg-blue-400 p-4 flex-1">Right</div>
</div>
```

In this example:
- Mobile screens par column layout (stacked)
- Medium screens (md) aur larger screens par row layout (side by side)

## Practice Exercise

Ek flexbox layout banao:
- 3 boxes with different colors
- Center boxes vertically and space them evenly
- On mobile, stack them vertically
- On desktop, place them horizontally

```html
<div class="flex flex-col md:flex-row justify-evenly items-center gap-4 min-h-64 bg-gray-100 p-4">
  <div class="bg-blue-500 text-white p-8 rounded">Box 1</div>
  <div class="bg-purple-500 text-white p-8 rounded">Box 2</div>
  <div class="bg-pink-500 text-white p-8 rounded">Box 3</div>
</div>
``` 