# Position Utilities in Tailwind CSS

Position utilities in Tailwind CSS help you control how elements are positioned on the page. These are powerful tools for creating complex layouts, overlays, sticky headers, and more.

## Basic Position Classes

| Class | Kya karta hai |
|-------|---------------|
| `static` | Default position (no effect) |
| `relative` | Element ko apni default jagah se shift kar sakte ho |
| `absolute` | Nearest relative parent ke hisaab se place hota hai |
| `fixed` | Viewport ke hisaab se place hota hai (scroll hone par bhi position same rahega) |
| `sticky` | Scroll ke time ek jagah chipak jata hai |

## Positioning with Top, Right, Bottom, Left

Position set karne ke baad, aap element ki exact position define kar sakte hain:

| Class | Effect |
|-------|--------|
| `top-0` | Top edge ko parent/viewport ke top se align karega |
| `right-0` | Right edge ko parent/viewport ke right se align karega |
| `bottom-0` | Bottom edge ko parent/viewport ke bottom se align karega |
| `left-0` | Left edge ko parent/viewport ke left se align karega |

Distance values bhi use kar sakte hain:

| Class | Effect |
|-------|--------|
| `top-4` | Top se 1rem (16px) ka gap |
| `right-8` | Right se 2rem (32px) ka gap |
| `inset-4` | All sides pe 1rem ka gap |
| `inset-y-4` | Top aur bottom pe 1rem gap |
| `inset-x-8` | Left aur right pe 2rem gap |

## Example: Absolute Positioning

```html
<div class="relative h-64 bg-gray-100">
  <div class="absolute top-4 left-4 bg-red-300 p-4">Top Left</div>
  <div class="absolute top-4 right-4 bg-green-300 p-4">Top Right</div>
  <div class="absolute bottom-4 left-4 bg-blue-300 p-4">Bottom Left</div>
  <div class="absolute bottom-4 right-4 bg-yellow-300 p-4">Bottom Right</div>
  <div class="absolute inset-0 m-auto w-24 h-24 bg-purple-300 p-4">Center</div>
</div>
```

Important: Absolute positioning ke liye, parent element ko `relative` hona zaroori hai.

## Sticky Positioning

Sticky headers, sidebars ya navigation banane ke liye:

```html
<header class="sticky top-0 bg-white shadow-md p-4 z-50">
  I'm a sticky header that stays at the top when scrolling
</header>
<div class="h-screen bg-gray-100 p-4">
  Scroll down to see the sticky header
</div>
```

Sticky element scroll karte waqt top-0 position pe chipak jayega.

## Fixed Positioning

Fixed elements viewport ke relative position pe rahte hain, aur scroll karne par bhi position change nahi hote:

```html
<div class="fixed bottom-4 right-4 bg-blue-500 text-white p-4 rounded-full shadow-lg">
  Chat Button (always visible)
</div>
```

Use cases:
- Fixed headers/footers
- Chat/help buttons
- Notification banners

## Z-Index (Layering)

Z-index elements ki layering control karta hai (which element appears on top):

| Class | Value |
|-------|-------|
| `z-0` | z-index: 0 |
| `z-10` | z-index: 10 |
| `z-20` | z-index: 20 |
| `z-30` | z-index: 30 |
| `z-40` | z-index: 40 |
| `z-50` | z-index: 50 |
| `z-auto` | z-index: auto |

Example:
```html
<div class="relative h-48">
  <div class="absolute top-0 left-0 w-32 h-32 bg-blue-300 z-0">Behind</div>
  <div class="absolute top-8 left-8 w-32 h-32 bg-red-300 z-10">In front</div>
</div>
```

## Complete Example: Modal Overlay

```html
<div class="relative h-64 bg-gray-100 overflow-hidden">
  <!-- Page content -->
  <p class="p-4">This is the page content</p>
  
  <!-- Modal overlay -->
  <div class="absolute inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50">
    <div class="bg-white p-6 rounded-lg shadow-xl max-w-md">
      <h2 class="text-xl font-bold mb-4">Modal Title</h2>
      <p class="mb-4">This is a modal that uses absolute positioning and z-index.</p>
      <button class="bg-blue-500 text-white px-4 py-2 rounded">Close</button>
    </div>
  </div>
</div>
```

## Practical Positioning Playground

Yahan ek complete example hai jisme position utilities ka use kiya gaya hai:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Tailwind Position Utilities</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <!-- Sticky Header -->
  <header class="sticky top-0 bg-yellow-300 p-4 shadow z-50">
    <h1 class="text-xl font-bold">Sticky Header (Position: sticky)</h1>
  </header>

  <!-- Main Section -->
  <div class="relative bg-white p-6 mt-4 max-w-3xl mx-auto shadow-lg min-h-[200px]">
    <h2 class="text-lg font-semibold mb-4">Relative Container</h2>

    <!-- Absolute Box inside relative -->
    <div class="absolute top-4 right-4 bg-red-400 text-white px-4 py-2 rounded shadow-lg z-10">
      Absolute Box
    </div>

    <p class="text-gray-700">
      Ye container `relative` hai. Iske andar jo red box hai, wo `absolute` hai and is container ke hisaab se placed hai.
    </p>
  </div>

  <!-- Fixed Box -->
  <div class="fixed bottom-4 right-4 bg-purple-600 text-white px-5 py-2 rounded shadow-lg z-40">
    Fixed Box (always on screen)
  </div>

  <!-- Z-Index Playground -->
  <div class="relative mt-20 max-w-3xl mx-auto h-48 bg-green-100 shadow-inner p-4">
    <div class="absolute top-4 left-4 bg-green-500 text-white p-4 z-10">z-10 Box</div>
    <div class="absolute top-8 left-8 bg-green-700 text-white p-4 z-0">z-0 Box</div>
    <p class="mt-32 text-gray-800">Z-index example: green box upar hai kyunki z-10 hai.</p>
  </div>

  <!-- Spacer for scroll -->
  <div class="h-[500px]"></div>

</body>
</html>
```

## Practice Tasks

1. Create a full-screen overlay with a centered modal
2. Create a sticky sidebar that stays visible when scrolling
3. Create a dropdown menu with absolute positioning
4. Create a "back to top" button that stays fixed at the bottom right

**Tip:** Always remember the parent-child relationship with positioning:
- Absolute elements are positioned relative to their nearest positioned ancestor
- If no positioned ancestor exists, they position relative to the document body