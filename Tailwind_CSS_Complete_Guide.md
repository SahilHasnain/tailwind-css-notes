# Comprehensive Tailwind CSS Guide

## Table of Contents
1. [Introduction to Tailwind CSS](#introduction)
2. [Installation](#installation)
3. [Core Concepts & Syntax](#core-concepts)
4. [Typography](#typography)
5. [Layout Systems](#layout-systems)
   - [Flexbox](#flexbox)
   - [Grid](#grid)
6. [Spacing & Sizing](#spacing-sizing)
7. [Colors & Backgrounds](#colors-backgrounds)
8. [Borders & Shadows](#borders-shadows)
9. [Responsive Design](#responsive-design)
10. [Pseudo-Classes](#pseudo-classes)
11. [Positioning](#positioning)
12. [Transitions & Animations](#transitions-animations)
13. [Customization](#customization)
14. [Dark Mode](#dark-mode)
15. [Performance Optimization](#performance)
16. [Best Practices](#best-practices)
17. [Frameworks Comparison](#frameworks-comparison)

## <a id="introduction"></a>Introduction to Tailwind CSS

Tailwind CSS is a utility-first CSS framework that enables rapid UI development through composable, low-level utility classes that let you build custom designs without leaving your HTML.

**Key Features:**
- **Utility-first:** Apply single-purpose classes directly in your markup
- **Responsive:** Built-in responsive design system
- **Component-friendly:** Extract reusable patterns with @apply
- **Customizable:** Tailwind adapts to your design system
- **Performance focused:** Only generates the CSS you use

**Philosophy:**
Unlike component-based frameworks like Bootstrap, Tailwind doesn't provide pre-designed components. Instead, it provides atomic utility classes that you compose to create your own designs.

## <a id="installation"></a>Installation

### CDN Installation (Quick Start)
```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://cdn.tailwindcss.com"></script>
</head>
```

### NPM Installation (Recommended)
```bash
# Create package.json if you don't have one
npm init -y

# Install Tailwind CSS, PostCSS and autoprefixer
npm install -D tailwindcss postcss autoprefixer

# Generate tailwind.config.js and postcss.config.js
npx tailwindcss init -p
```

Then create a CSS file (e.g., `src/input.css`):
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Configure content paths in `tailwind.config.js`:
```js
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Process your CSS:
```bash
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```

Link in your HTML:
```html
<head>
  <link href="/dist/output.css" rel="stylesheet">
</head>
```

## <a id="core-concepts"></a>Core Concepts & Syntax

### Utility-First Approach
Tailwind uses short, descriptive class names that each serve a single purpose:

```html
<!-- Traditional CSS approach -->
<div class="card">
  <div class="card-header">Title</div>
  <div class="card-body">Content</div>
</div>

<!-- Tailwind approach -->
<div class="rounded-lg shadow-md overflow-hidden">
  <div class="px-6 py-4 bg-gray-100 font-bold">Title</div>
  <div class="px-6 py-4">Content</div>
</div>
```

### Class Naming Convention
Tailwind classes follow a consistent pattern:
- `property-value`: e.g., `bg-blue-500`, `p-4`
- `{breakpoint}:property-value`: e.g., `md:flex-row`
- `{state}:property-value`: e.g., `hover:bg-blue-700`

### Combining Classes
Tailwind encourages composing multiple utility classes:

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
  Button
</button>
```

## <a id="typography"></a>Typography

### Font Family
```html
<p class="font-sans">Sans-serif text</p>
<p class="font-serif">Serif text</p>
<p class="font-mono">Monospace text</p>
```

### Font Size
```html
<p class="text-xs">Extra small</p>
<p class="text-sm">Small</p>
<p class="text-base">Base</p>
<p class="text-lg">Large</p>
<p class="text-xl">Extra large</p>
<p class="text-2xl">2xl</p>
<!-- Up to text-9xl -->
```

### Font Weight
```html
<p class="font-thin">Thin</p>
<p class="font-normal">Normal</p>
<p class="font-medium">Medium</p>
<p class="font-semibold">Semibold</p>
<p class="font-bold">Bold</p>
<p class="font-extrabold">Extra Bold</p>
```

### Text Alignment
```html
<p class="text-left">Left aligned</p>
<p class="text-center">Center aligned</p>
<p class="text-right">Right aligned</p>
<p class="text-justify">Justified</p>
```

### Text Color
```html
<p class="text-blue-500">Blue text</p>
<p class="text-red-600">Red text</p>
<p class="text-gray-800">Dark gray text</p>
```

### Line Height
```html
<p class="leading-none">Leading none</p>
<p class="leading-tight">Leading tight</p>
<p class="leading-normal">Leading normal</p>
<p class="leading-relaxed">Leading relaxed</p>
<p class="leading-loose">Leading loose</p>
```

### Letter Spacing
```html
<p class="tracking-tighter">Tighter</p>
<p class="tracking-normal">Normal</p>
<p class="tracking-wider">Wider</p>
```

### Text Decoration
```html
<p class="underline">Underlined</p>
<p class="line-through">Strikethrough</p>
<p class="no-underline">No underline</p>
```

### Text Transform
```html
<p class="uppercase">Uppercase</p>
<p class="lowercase">Lowercase</p>
<p class="capitalize">Capitalize</p>
<p class="normal-case">Normal case</p>
```

## <a id="layout-systems"></a>Layout Systems

### <a id="flexbox"></a>Flexbox

Flexbox is a one-dimensional layout system for arranging items in rows or columns.

#### Creating a Flex Container
```html
<div class="flex">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

#### Flex Direction
```html
<div class="flex flex-row"><!-- Default: left to right --></div>
<div class="flex flex-row-reverse"><!-- Right to left --></div>
<div class="flex flex-col"><!-- Top to bottom --></div>
<div class="flex flex-col-reverse"><!-- Bottom to top --></div>
```

#### Justify Content (Main Axis)
```html
<div class="flex justify-start"><!-- Default --></div>
<div class="flex justify-center"><!-- Center --></div>
<div class="flex justify-end"><!-- End --></div>
<div class="flex justify-between"><!-- Space between --></div>
<div class="flex justify-around"><!-- Space around --></div>
<div class="flex justify-evenly"><!-- Space evenly --></div>
```

#### Align Items (Cross Axis)
```html
<div class="flex items-start"><!-- Top --></div>
<div class="flex items-center"><!-- Center --></div>
<div class="flex items-end"><!-- Bottom --></div>
<div class="flex items-stretch"><!-- Stretch (default) --></div>
<div class="flex items-baseline"><!-- Baseline --></div>
```

#### Flex Wrap
```html
<div class="flex flex-nowrap"><!-- Default: no wrapping --></div>
<div class="flex flex-wrap"><!-- Wrap --></div>
<div class="flex flex-wrap-reverse"><!-- Wrap reverse --></div>
```

#### Flex Item Sizing
```html
<div class="flex">
  <div class="flex-1"><!-- Grow and shrink --></div>
  <div class="flex-auto"><!-- Grow and shrink, considering initial size --></div>
  <div class="flex-initial"><!-- Shrink but don't grow --></div>
  <div class="flex-none"><!-- Don't grow or shrink --></div>
</div>
```

#### Order
```html
<div class="flex">
  <div class="order-3">First in HTML, third visually</div>
  <div class="order-1">Second in HTML, first visually</div>
  <div class="order-2">Third in HTML, second visually</div>
</div>
```

### <a id="grid"></a>Grid

Grid is a two-dimensional layout system that handles both rows and columns simultaneously.

#### Creating a Grid
```html
<div class="grid grid-cols-3 gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
  <div>Item 4</div>
  <div>Item 5</div>
  <div>Item 6</div>
</div>
```

#### Grid Template Columns
```html
<div class="grid grid-cols-1"><!-- 1 column --></div>
<div class="grid grid-cols-3"><!-- 3 equal columns --></div>
<div class="grid grid-cols-none"><!-- No explicit grid columns --></div>
<div class="grid grid-cols-[200px_1fr_2fr]"><!-- Custom grid template --></div>
```

#### Grid Column/Row Spanning
```html
<div class="grid grid-cols-3">
  <div class="col-span-2">Spans 2 columns</div>
  <div>Regular cell</div>
  <div class="col-span-3">Spans full width</div>
  <div class="row-span-2">Spans 2 rows</div>
</div>
```

#### Grid Gap
```html
<div class="grid grid-cols-3 gap-4"><!-- Gap on both axes --></div>
<div class="grid grid-cols-3 gap-x-4"><!-- Gap on x-axis only --></div>
<div class="grid grid-cols-3 gap-y-4"><!-- Gap on y-axis only --></div>
```

#### Grid Placement
```html
<div class="grid grid-cols-3">
  <div class="col-start-2 col-end-4">From column 2 to 4</div>
  <div class="row-start-1 row-end-3">From row 1 to 3</div>
</div>
```

## <a id="spacing-sizing"></a>Spacing & Sizing

### Padding
```html
<div class="p-4"><!-- All sides --></div>
<div class="px-4"><!-- Left + Right --></div>
<div class="py-4"><!-- Top + Bottom --></div>
<div class="pt-4"><!-- Top only --></div>
<div class="pr-4"><!-- Right only --></div>
<div class="pb-4"><!-- Bottom only --></div>
<div class="pl-4"><!-- Left only --></div>
```

### Margin
```html
<div class="m-4"><!-- All sides --></div>
<div class="mx-4"><!-- Left + Right --></div>
<div class="my-4"><!-- Top + Bottom --></div>
<div class="mt-4"><!-- Top only --></div>
<div class="mr-4"><!-- Right only --></div>
<div class="mb-4"><!-- Bottom only --></div>
<div class="ml-4"><!-- Left only --></div>
<div class="mx-auto"><!-- Center horizontally --></div>
```

### Width
```html
<div class="w-full">100% width</div>
<div class="w-screen">100vw</div>
<div class="w-1/2">50% width</div>
<div class="w-1/3">33.33% width</div>
<div class="w-64">16rem (256px)</div>
<div class="w-auto">Auto width</div>
```

### Height
```html
<div class="h-full">100% height</div>
<div class="h-screen">100vh</div>
<div class="h-64">16rem (256px)</div>
<div class="h-auto">Auto height</div>
```

### Min/Max Dimensions
```html
<div class="min-w-full">Min width 100%</div>
<div class="max-w-md">Max width medium container</div>
<div class="min-h-screen">Min height 100vh</div>
<div class="max-h-screen">Max height 100vh</div>
```

## <a id="colors-backgrounds"></a>Colors & Backgrounds

### Background Color
```html
<div class="bg-red-500">Red background</div>
<div class="bg-blue-200">Light blue background</div>
<div class="bg-gray-900">Dark gray background</div>
<div class="bg-white">White background</div>
<div class="bg-transparent">Transparent background</div>
```

### Background Opacity
```html
<div class="bg-blue-500 bg-opacity-75">75% opacity blue</div>
<div class="bg-blue-500 bg-opacity-50">50% opacity blue</div>
<div class="bg-blue-500 bg-opacity-25">25% opacity blue</div>
```

### Gradient Backgrounds
```html
<div class="bg-gradient-to-r from-blue-500 to-purple-500">
  Blue to purple gradient
</div>

<div class="bg-gradient-to-r from-green-400 via-blue-500 to-purple-600">
  Green to blue to purple gradient
</div>
```

### Background Size & Position
```html
<div class="bg-auto">Auto size</div>
<div class="bg-cover">Cover</div>
<div class="bg-contain">Contain</div>
<div class="bg-center">Center</div>
<div class="bg-top">Top</div>
```

## <a id="borders-shadows"></a>Borders & Shadows

### Border Width
```html
<div class="border">Default border</div>
<div class="border-2">Medium border</div>
<div class="border-4">Thick border</div>
<div class="border-t">Top border</div>
<div class="border-r">Right border</div>
<div class="border-b">Bottom border</div>
<div class="border-l">Left border</div>
```

### Border Color
```html
<div class="border border-red-500">Red border</div>
<div class="border border-blue-300">Light blue border</div>
<div class="border border-gray-700">Dark gray border</div>
```

### Border Radius
```html
<div class="rounded">Small radius</div>
<div class="rounded-md">Medium radius</div>
<div class="rounded-lg">Large radius</div>
<div class="rounded-full">Full/circular radius</div>
<div class="rounded-t">Top corners only</div>
<div class="rounded-tl">Top left corner only</div>
```

### Box Shadow
```html
<div class="shadow-sm">Small shadow</div>
<div class="shadow">Default shadow</div>
<div class="shadow-md">Medium shadow</div>
<div class="shadow-lg">Large shadow</div>
<div class="shadow-xl">Extra large shadow</div>
<div class="shadow-2xl">2x extra large shadow</div>
<div class="shadow-inner">Inner shadow</div>
<div class="shadow-none">No shadow</div>
```

## <a id="responsive-design"></a>Responsive Design

Tailwind uses a mobile-first approach with breakpoint prefixes:

```html
<!-- Stacked on mobile, side by side on medium screens and up -->
<div class="flex flex-col md:flex-row">
  <div class="w-full md:w-1/2">First column (full width on mobile, half on md+)</div>
  <div class="w-full md:w-1/2">Second column (full width on mobile, half on md+)</div>
</div>
```

### Breakpoint Prefixes
- `sm`: Small screens (640px and up)
- `md`: Medium screens (768px and up)
- `lg`: Large screens (1024px and up)
- `xl`: Extra large screens (1280px and up)
- `2xl`: 2x extra large screens (1536px and up)

### Responsive Examples

**Responsive Typography:**
```html
<h1 class="text-2xl md:text-3xl lg:text-4xl">Responsive heading</h1>
```

**Responsive Spacing:**
```html
<div class="p-4 md:p-8 lg:p-12">
  Increasing padding as screen size grows
</div>
```

**Responsive Visibility:**
```html
<div class="hidden md:block">Visible only on medium screens and up</div>
<div class="md:hidden">Hidden on medium screens and up</div>
```

## <a id="pseudo-classes"></a>Pseudo-Classes

Tailwind makes it easy to style elements based on their state with modifier prefixes.

### Mouse States
```html
<button class="bg-blue-500 hover:bg-blue-700">Hover me</button>
<button class="bg-gray-200 active:bg-gray-400">Click me</button>
<a class="text-blue-500 visited:text-purple-500">Link</a>
```

### Focus States
```html
<input class="border focus:border-blue-500 focus:ring-2 focus:ring-blue-200" />
<button class="focus:outline-none focus:ring-2 focus:ring-blue-500">Focus me</button>
```

### Form States
```html
<input class="disabled:bg-gray-200 disabled:opacity-75" disabled />
<input type="checkbox" class="checked:bg-blue-500" />
<input class="invalid:border-red-500 valid:border-green-500" />
```

### Parent-State Modifiers
```html
<div class="group hover:bg-blue-100">
  <p class="text-gray-800 group-hover:text-blue-600">
    This text changes when parent is hovered
  </p>
</div>
```

### Media Query Modifiers
```html
<div class="dark:bg-gray-800 dark:text-white">
  Changes color in dark mode
</div>
```

## <a id="positioning"></a>Positioning

### Position Type
```html
<div class="static">Static (default)</div>
<div class="relative">Relative</div>
<div class="absolute">Absolute</div>
<div class="fixed">Fixed</div>
<div class="sticky">Sticky</div>
```

### Positioning
```html
<div class="relative">
  <div class="absolute top-0 right-0">Top right</div>
  <div class="absolute bottom-0 left-0">Bottom left</div>
  <div class="absolute inset-0">Fill parent</div>
  <div class="absolute inset-x-0">Full width, original height</div>
  <div class="absolute inset-y-0">Full height, original width</div>
</div>
```

### Z-Index
```html
<div class="z-0">z-index 0</div>
<div class="z-10">z-index 10</div>
<div class="z-20">z-index 20</div>
<div class="z-50">z-index 50</div>
<div class="z-auto">z-index auto</div>
```

## <a id="transitions-animations"></a>Transitions & Animations

### Transitions
```html
<button class="transition duration-300 ease-in-out bg-blue-500 hover:bg-blue-700">
  Smooth transition
</button>
```

**Transition Properties:**
```html
<div class="transition-colors">Transition colors only</div>
<div class="transition-opacity">Transition opacity only</div>
<div class="transition-transform">Transition transforms only</div>
<div class="transition-all">Transition all properties</div>
<div class="transition-none">No transitions</div>
```

**Duration:**
```html
<div class="duration-75">75ms</div>
<div class="duration-100">100ms</div>
<div class="duration-300">300ms</div>
<div class="duration-700">700ms</div>
```

**Timing Function:**
```html
<div class="ease-linear">Linear</div>
<div class="ease-in">Ease in</div>
<div class="ease-out">Ease out</div>
<div class="ease-in-out">Ease in-out</div>
```

**Delay:**
```html
<div class="delay-100">100ms delay</div>
<div class="delay-300">300ms delay</div>
<div class="delay-700">700ms delay</div>
```

### Animations
```html
<div class="animate-spin">Spinning animation</div>
<div class="animate-ping">Ping animation</div>
<div class="animate-pulse">Pulse animation</div>
<div class="animate-bounce">Bounce animation</div>
```

### Transforms
```html
<div class="scale-75">Scaled down</div>
<div class="scale-125">Scaled up</div>
<div class="rotate-45">Rotated 45 degrees</div>
<div class="translate-x-4">Translated right</div>
<div class="translate-y-4">Translated down</div>
<div class="skew-x-12">Skewed on X axis</div>
```

**Transform on Hover:**
```html
<div class="hover:scale-110 transition">
  Scales up on hover
</div>
```

## <a id="customization"></a>Customization

Tailwind is highly customizable through its configuration file, `tailwind.config.js`:

```js
module.exports = {
  content: [
    './src/**/*.{html,js,jsx,tsx}',
  ],
  theme: {
    // Override the default theme
    colors: {
      'primary': '#3490dc',
      'secondary': '#ffed4a',
      'danger': '#e3342f',
    },
    // Extend the default theme
    extend: {
      spacing: {
        '72': '18rem',
        '84': '21rem',
        '96': '24rem',
      },
      borderRadius: {
        'xl': '1rem',
        '2xl': '2rem',
      },
      fontFamily: {
        'heading': ['Montserrat', 'sans-serif'],
        'body': ['Open Sans', 'sans-serif'],
      },
    },
  },
  plugins: [
    // Add custom plugins
    require('@tailwindcss/forms'),
    require('@tailwindcss/typography'),
  ],
  variants: {
    extend: {
      // Enable more variant combinations
      backgroundColor: ['active', 'disabled'],
      opacity: ['disabled'],
    }
  },
}
```

### Using Custom Utilities with @apply

You can extract common utility patterns into CSS components using `@apply`:

```css
/* In your CSS file */
@tailwind base;
@tailwind components;

@layer components {
  .btn {
    @apply py-2 px-4 rounded font-semibold focus:outline-none focus:ring-2 focus:ring-offset-2;
  }
  
  .btn-primary {
    @apply bg-blue-500 hover:bg-blue-700 text-white;
  }
  
  .btn-secondary {
    @apply bg-gray-200 hover:bg-gray-300 text-gray-800;
  }
}

@tailwind utilities;
```

```html
<!-- In your HTML -->
<button class="btn btn-primary">Primary Button</button>
<button class="btn btn-secondary">Secondary Button</button>
```

## <a id="dark-mode"></a>Dark Mode

### Configuration

In `tailwind.config.js`:
```js
module.exports = {
  darkMode: 'media', // System preference (default)
  // OR
  darkMode: 'class', // Manual toggle with a 'dark' class
}
```

### Using Dark Mode Variants

```html
<div class="bg-white dark:bg-gray-800 text-black dark:text-white">
  This content adapts to dark mode
</div>
```

### Toggle Implementation (Class Strategy)

```html
<button id="toggle">Toggle Dark Mode</button>

<script>
  const toggle = document.getElementById('toggle');
  
  // Check saved theme or system preference
  if (localStorage.theme === 'dark' || 
      (!localStorage.theme && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
    document.documentElement.classList.add('dark');
  }
  
  // Toggle theme
  toggle.addEventListener('click', () => {
    if (document.documentElement.classList.contains('dark')) {
      document.documentElement.classList.remove('dark');
      localStorage.theme = 'light';
    } else {
      document.documentElement.classList.add('dark');
      localStorage.theme = 'dark';
    }
  });
</script>
```

### Preventing Flash

```html
<script>
  // Add to <head>
  if (localStorage.theme === 'dark' || 
      (!localStorage.theme && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
    document.documentElement.classList.add('dark');
  }
</script>
```

## <a id="performance"></a>Performance Optimization

### PurgeCSS Integration

The most important optimization is removing unused CSS:

```js
// tailwind.config.js
module.exports = {
  content: [
    './src/**/*.{html,js,jsx,tsx}',
  ],
  theme: {
    // Your theme config
  },
  plugins: [],
}
```

### JIT Mode

Tailwind v3.0+ uses Just-in-Time mode by default, which generates CSS on-demand:

**Benefits:**
- Smaller CSS files
- Faster build times
- Support for arbitrary values (`text-[22px]`, `mt-[33px]`)

### Minification

```js
// postcss.config.js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
    ...(process.env.NODE_ENV === 'production' ? { cssnano: {} } : {})
  }
}
```

### Disable Unused Features

```js
// tailwind.config.js
module.exports = {
  // ...
  corePlugins: {
    float: false,
    objectFit: false,
    // Disable other unused features
  }
}
```

## <a id="best-practices"></a>Best Practices

### Extract Components for Reusability

Instead of repeating complex utility combinations, extract them:

```jsx
// React example
function Button({ children, primary }) {
  const baseStyles = "font-bold py-2 px-4 rounded";
  const primaryStyles = "bg-blue-500 hover:bg-blue-700 text-white";
  const secondaryStyles = "bg-gray-200 hover:bg-gray-300 text-gray-800";
  
  return (
    <button 
      className={`${baseStyles} ${primary ? primaryStyles : secondaryStyles}`}
    >
      {children}
    </button>
  );
}
```

### Responsive Design Approach

Follow a mobile-first approach:
1. Style for mobile by default (no breakpoint prefix)
2. Add larger-screen styles with breakpoint prefixes

```html
<div class="flex flex-col md:flex-row">
  <!-- Mobile: Column, Desktop: Row -->
</div>
```

### Maintain Accessibility

Always ensure your designs are accessible:

```html
<!-- Good contrast -->
<p class="text-gray-900 bg-white">Dark text on white</p>

<!-- Proper focus states -->
<button class="focus:outline-none focus:ring-2 focus:ring-blue-500">
  Accessible Button
</button>
```

### Use Consistent Spacing

Tailwind's spacing scale is designed to be coherent. Stick to it:

```html
<!-- Use Tailwind's spacing scale -->
<div class="p-4 mb-6 gap-2"></div>

<!-- Avoid arbitrary values when possible -->
<div class="p-[17px] mb-[27px]"></div>
```

## <a id="frameworks-comparison"></a>Frameworks Comparison

### Tailwind CSS vs Bootstrap

**Tailwind CSS:**
- Utility-first approach
- Highly customizable
- No built-in components
- Smaller file size (when purged)
- More flexibility in design

**Bootstrap:**
- Component-based approach
- Pre-designed components
- Recognizable "Bootstrap look"
- JavaScript functionality included
- Faster initial development

**When to choose Tailwind:**
- For unique, custom designs
- When you want to avoid the "Bootstrap look"
- For projects requiring design flexibility
- When performance is critical

### Tailwind CSS vs Bulma

**Tailwind CSS:**
- Utility classes for granular control
- More verbose HTML
- No opinion on design
- Mobile-first approach

**Bulma:**
- Modern Flexbox-based framework
- Semantic class names
- No JavaScript dependencies
- Modular architecture

### Development Workflow Comparison

**Tailwind Workflow:**
1. Install and configure Tailwind
2. Build HTML with utility classes
3. Extract components using @apply as needed
4. Configure PurgeCSS for production
5. Customize design tokens as needed

**Component Framework Workflow:**
1. Install framework
2. Import pre-built components
3. Override styles as needed
4. Customize using framework's options
5. Add custom CSS for unique elements 