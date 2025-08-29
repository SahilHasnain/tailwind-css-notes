# Backgrounds, Borders & Shadows in Tailwind CSS

This section covers how to style the visual aspects of elements including backgrounds, borders, shadows, and more.

## 1. Background Colors

Tailwind me background color lagana bahut easy hai:

```html
<div class="bg-blue-500 text-white p-4">Blue background</div>
<div class="bg-yellow-300 text-black p-4">Yellow background</div>
```

| Example | Effect |
|---------|--------|
| `bg-red-500` | Red background |
| `bg-green-700` | Dark green background |
| `bg-gray-200` | Light gray background |

### Background Color Opacity

```html
<div class="bg-blue-500 bg-opacity-50 text-white p-4">50% Transparent Blue</div>
```

In newer Tailwind versions (v3+):
```html
<div class="bg-blue-500/50 text-white p-4">50% Transparent Blue</div>
```

## 2. Background Image

CDN version me tum custom CSS ke through ya inline style se background image laga sakte ho.

```html
<div class="bg-cover bg-center h-64" style="background-image: url('https://picsum.photos/600/400');">
  <h1 class="text-white text-3xl p-4">Image Background</h1>
</div>
```

| Class | Meaning |
|-------|---------|
| `bg-cover` | Image ko full area cover karna |
| `bg-center` | Center se image align karna |
| `h-64` | Height set karna (16rem = 256px) |

## 3. Background Gradient

```html
<div class="bg-gradient-to-r from-purple-400 via-pink-500 to-red-500 p-6 rounded-lg shadow-lg text-white">
  <h2 class="text-2xl font-bold mb-2">Gradient Box</h2>
  <p>This box has background gradient, border radius and shadow. Stylish na?</p>
</div>
```

| Class | Effect |
|-------|--------|
| `bg-gradient-to-r` | Left to right gradient |
| `bg-gradient-to-b` | Top to bottom gradient |
| `bg-gradient-to-br` | Top-left to bottom-right |
| `from-purple-400` | Starting color |
| `via-pink-500` | Middle color (optional) |
| `to-red-500` | Ending color |

## 4. Borders

```html
<div class="border border-red-500 p-4 rounded-lg">
  Border with red color and rounded corners
</div>
```

| Class | Effect |
|-------|--------|
| `border` → 1px border sab sides par |
| `border-2` → 2px thick |
| `border-t` → Sirf top |
| `border-l` → Sirf left |
| `border-red-500` → Red border color |
| `border-dashed` | Dashed border style |
| `border-dotted` | Dotted border style |

## 5. Border Radius (Rounded Corners)

```html
<div class="bg-white p-4 rounded-lg">Rounded corners</div>
```

| Class | Effect |
|-------|--------|
| `rounded` | Small radius (0.25rem) |
| `rounded-md` | Medium radius (0.375rem) |
| `rounded-lg` | Large radius (0.5rem) |
| `rounded-xl` | Extra large radius (0.75rem) |
| `rounded-2xl` | 2x large radius (1rem) |
| `rounded-full` | Circular (50%) |
| `rounded-t-lg` | Top corners only |
| `rounded-b-lg` | Bottom corners only |

## 6. Shadows

```html
<div class="p-6 bg-white shadow-md rounded-md">
  Yeh ek shadow wala box hai
</div>
```

| Class | Shadow Strength |
|-------|-----------------|
| `shadow-sm` | Small shadow |
| `shadow` | Default |
| `shadow-md` | Medium |
| `shadow-lg` | Large |
| `shadow-xl` | Extra Large |
| `shadow-2xl` | 2x Large |
| `shadow-inner` | Inner shadow |
| `shadow-none` | No shadow |

## Complete Example (With Borders, Backgrounds, and Shadows)

```html
<div class="max-w-sm mx-auto mt-10 bg-gradient-to-r from-purple-400 via-pink-500 to-red-500 p-1 rounded-lg shadow-lg">
  <div class="bg-white p-6 rounded-lg">
    <h2 class="text-xl font-bold text-gray-800 mb-3">Styled Card</h2>
    <p class="text-gray-600">This card uses multiple Tailwind utilities for styling including gradient border, shadows, and rounded corners.</p>
    <button class="mt-4 px-4 py-2 bg-purple-500 text-white rounded hover:bg-purple-700">
      Learn More
    </button>
  </div>
</div>
```

## Practice Project

Try creating the following:

1. Three boxes with different styling:
   - One with solid background color
   - One with image background
   - One with gradient background

2. Each box should have:
   - Different border styles (color + thickness)
   - Different shadow styles
   - Different rounded corner styles 

## Practice Project Solution

```jsx
<div class="p-8 flex flex-col items-center">
      <h1 class="text-3xl font-bold mb-8">Styled Boxes Demonstration</h1>
      
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8 w-full max-w-5xl">
      
        <div class="flex flex-col items-center">
          <h2 class="text-xl font-semibold mb-4">Solid Background</h2>
          <div 
            class="
              bg-blue-500 
              border-4 border-blue-800 
              shadow-lg 
              rounded-lg
              w-full h-64
              flex items-center justify-center
              text-white font-bold text-xl
            "
          >
            Solid Color Box
          </div>
          <div class="mt-2 text-sm text-gray-600">
            <p>• Solid blue background</p>
            <p>• Thick blue border</p>
            <p>• Medium shadow</p>
            <p>• Standard rounded corners</p>
          </div>
        </div>
        
       
        <div class="flex flex-col items-center">
          <h2 class="text-xl font-semibold mb-4">Image Background</h2>
          <div 
            class="bg-cover bg-center
                   border-2 border-dashed border-purple-800 
                   shadow-2xl shadow-purple-300
                   rounded-2xl
                   w-full h-64
                   flex items-center justify-center
                   text-white font-bold text-xl
                   relative
                   overflow-hidden"
            style={{backgroundImage: "url('/api/placeholder/400/320')"}}
            
          >
            <div class="absolute inset-0 bg-black bg-opacity-30"></div>
            <span class="z-10 relative">Image Box</span>
          </div>
          <div class="mt-2 text-sm text-gray-600">
            <p>• Image background</p>
            <p>• Dashed purple border</p>
            <p>• Large colored shadow</p>
            <p>• More rounded corners</p>
          </div>
        </div>
        
        
        <div class="flex flex-col items-center">
          <h2 class="text-xl font-semibold mb-4">Gradient Background</h2>
          <div 
            class="
              bg-gradient-to-br from-pink-500 via-red-500 to-yellow-500
              border-8 border-double border-red-600
              shadow-inner shadow-red-900
              rounded-full
              w-full h-64
              flex items-center justify-center
              text-white font-bold text-xl
            "
          >
            Gradient Box
          </div>
          <div class="mt-2 text-sm text-gray-600">
            <p>• Gradient background</p>
            <p>• Double red border</p>
            <p>• Inner shadow</p>
            <p>• Fully rounded corners</p>
          </div>
        </div>
      </div>
      
      <div class="mt-12 p-6 bg-gray-100 rounded-lg w-full max-w-5xl">
        <h3 class="font-semibold mb-2">Styling Summary:</h3>
        <ul class="list-disc pl-5 space-y-2">
          <li><strong>Box 1:</strong> Solid background with standard shadow and border</li>
          <li><strong>Box 2:</strong> Image background with dashed border and colored external shadow</li>
          <li><strong>Box 3:</strong> Gradient background with double border, inner shadow, and circular shape</li>
        </ul>
      </div>
    </div>
  ```