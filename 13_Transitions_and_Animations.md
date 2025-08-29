# Transitions and Animations in Tailwind CSS

Transitions and Animations in Tailwind CSS help create smooth and engaging user interfaces. Ye interactive elements ko professional aur polished feel dete hain.

## Transitions in Tailwind

Transition classes elements ke state changes (like hover, focus) ko smooth banate hain.

### Basic Transition Classes

| Class | Description |
|-------|-------------|
| `transition` | Apply a transition to an element |
| `transition-all` | Apply to all properties |
| `transition-colors` | Apply to colors only |
| `transition-opacity` | Apply to opacity only |
| `transition-shadow` | Apply to shadow only |
| `transition-transform` | Apply to transform only |

### Transition Duration

Duration determines how long the transition takes:

| Class | Value |
|-------|-------|
| `duration-75` | 75ms |
| `duration-100` | 100ms |
| `duration-150` | 150ms |
| `duration-200` | 200ms |
| `duration-300` | 300ms |
| `duration-500` | 500ms |
| `duration-700` | 700ms |
| `duration-1000` | 1000ms (1 second) |

### Transition Timing Functions

Control the acceleration curve:

| Class | Description |
|-------|-------------|
| `ease-linear` | Constant speed |
| `ease-in` | Slow start, fast end |
| `ease-out` | Fast start, slow end |
| `ease-in-out` | Slow start and end, fast middle |

### Transition Delay

Delay before transition starts:

| Class | Value |
|-------|-------|
| `delay-75` | 75ms |
| `delay-100` | 100ms |
| `delay-150` | 150ms |
| `delay-300` | 300ms |
| `delay-500` | 500ms |
| `delay-700` | 700ms |
| `delay-1000` | 1000ms (1 second) |

### Example: Button with Smooth Hover Transition

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded transition duration-300 ease-in-out">
  Hover Me
</button>
```

## Transform Utilities in Tailwind

Transform utilities help with sizing, rotating, and moving elements. Yeh animations ke liye important hote hain.

### Transform Base Class

`transform` class is required to enable transformations:

```html
<div class="transform scale-110">
  I'm 10% larger than normal
</div>
```

### Scale (Size Change)

| Class | Effect |
|-------|--------|
| `scale-0` | Scale to 0 (invisible) |
| `scale-50` | Scale to 50% |
| `scale-75` | Scale to 75% |
| `scale-90` | Scale to 90% |
| `scale-100` | Default (100%) |
| `scale-110` | Scale to 110% |
| `scale-125` | Scale to 125% |
| `scale-150` | Scale to 150% |

You can scale X or Y independently with `scale-x-*` and `scale-y-*`

### Rotate (Spin Elements)

| Class | Effect |
|-------|--------|
| `rotate-0` | No rotation |
| `rotate-45` | Rotate 45 degrees clockwise |
| `rotate-90` | Rotate 90 degrees clockwise |
| `rotate-180` | Rotate 180 degrees (upside down) |
| `-rotate-45` | Rotate 45 degrees counter-clockwise |

### Translate (Move Elements)

| Class | Effect |
|-------|--------|
| `translate-x-4` | Move right 1rem |
| `-translate-x-4` | Move left 1rem |
| `translate-y-4` | Move down 1rem |
| `-translate-y-4` | Move up 1rem |
| `translate-x-1/2` | Move right 50% |
| `translate-y-full` | Move down 100% |

### Skew (Tilt Elements)

| Class | Effect |
|-------|--------|
| `skew-x-6` | Skew horizontally 6 degrees |
| `skew-y-3` | Skew vertically 3 degrees |
| `-skew-x-6` | Skew opposite direction |

## Built-in Animations in Tailwind

Tailwind me pre-defined animations hain that you can apply directly:

| Class | Effect |
|-------|--------|
| `animate-spin` | Rotating animation (360 degrees) |
| `animate-ping` | Scaling animation (pulse effect) |
| `animate-pulse` | Opacity pulsing effect |
| `animate-bounce` | Up and down bouncing |

### Animation Examples

Spinning loader:
```html
<div class="h-10 w-10 bg-blue-500 rounded-full animate-spin"></div>
```

Bouncing element:
```html
<div class="h-10 w-10 bg-green-500 rounded-full animate-bounce"></div>
```

Pulsing notification dot:
```html
<span class="h-3 w-3 bg-red-500 rounded-full animate-ping absolute"></span>
```

## Combining Transitions and Transforms

Most powerful effects combine transitions with transforms:

```html
<div class="transform hover:scale-110 transition duration-300 ease-in-out">
  I grow smoothly on hover
</div>
```

## Practical Examples

### Card Hover Effect

```html
<div class="max-w-sm mx-auto bg-white rounded-xl shadow-md overflow-hidden transform hover:scale-105 transition duration-300">
  <div class="p-6">
    <h2 class="font-bold text-xl mb-2">Card with Hover Effect</h2>
    <p class="text-gray-700">This card scales up slightly when hovered.</p>
  </div>
</div>
```

### Button Click Animation

```html
<button class="bg-blue-500 text-white px-4 py-2 rounded transform active:scale-95 transition duration-200">
  Click me (I shrink when clicked)
</button>
```

### Loading Spinner

```html
<div class="flex items-center justify-center">
  <div class="h-12 w-12 border-4 border-blue-200 border-t-blue-500 rounded-full animate-spin"></div>
  <span class="ml-3">Loading...</span>
</div>
```

### Image Hover Zoom Effect

```html
<div class="overflow-hidden rounded-lg">
  <img 
    src="https://source.unsplash.com/random/400x300" 
    alt="Random image" 
    class="w-full h-full transform hover:scale-110 transition duration-500"
  />
</div>
```

## Complete Example

Here's a mini animation playground that demonstrates various Tailwind animation capabilities:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Tailwind Animations</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 p-8">
  <div class="max-w-md mx-auto space-y-8">
    <h1 class="text-2xl font-bold text-center mb-6">Tailwind Animation Examples</h1>
    
    <!-- Hover Transitions -->
    <div class="bg-white p-6 rounded-lg shadow-md transform hover:scale-105 hover:bg-blue-50 transition duration-300">
      <h2 class="font-bold mb-2">Hover Effect</h2>
      <p class="text-gray-600">This card scales and changes color on hover.</p>
    </div>
    
    <!-- Built-in Animations -->
    <div class="bg-white p-6 rounded-lg shadow-md">
      <h2 class="font-bold mb-4">Built-in Animations</h2>
      <div class="flex justify-around">
        <div class="text-center">
          <div class="h-10 w-10 bg-blue-500 rounded-full animate-spin mx-auto"></div>
          <p class="mt-2 text-sm">spin</p>
        </div>
        <div class="text-center">
          <div class="h-10 w-10 bg-green-500 rounded-full animate-pulse mx-auto"></div>
          <p class="mt-2 text-sm">pulse</p>
        </div>
        <div class="text-center">
          <div class="h-10 w-10 bg-red-500 rounded-full animate-bounce mx-auto"></div>
          <p class="mt-2 text-sm">bounce</p>
        </div>
        <div class="text-center">
          <div class="relative">
            <div class="absolute h-10 w-10 bg-yellow-500 rounded-full animate-ping opacity-75"></div>
            <div class="relative h-10 w-10 bg-yellow-500 rounded-full"></div>
          </div>
          <p class="mt-2 text-sm">ping</p>
        </div>
      </div>
    </div>
    
    <!-- Buttons with Transitions -->
    <div class="bg-white p-6 rounded-lg shadow-md">
      <h2 class="font-bold mb-4">Interactive Buttons</h2>
      <div class="flex space-x-4 justify-center">
        <button class="bg-blue-500 hover:bg-blue-700 text-white px-4 py-2 rounded transition duration-300">
          Hover Me
        </button>
        <button class="bg-purple-500 text-white px-4 py-2 rounded transform active:scale-95 transition duration-200">
          Click Me
        </button>
      </div>
    </div>
  </div>
</body>
</html>
```

## Practice Tasks

1. Create a button that changes color smoothly on hover
2. Create a card that zooms slightly on hover
3. Create a loading spinner using `animate-spin`
4. Create a notification dot using `animate-ping`
5. Create an image that zooms on hover without overflowing its container 