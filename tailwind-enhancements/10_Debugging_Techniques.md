# Debugging Techniques for Tailwind CSS

This guide covers practical methods to troubleshoot common issues when working with Tailwind CSS.

## Browser DevTools

### Inspecting Elements
1. Right-click element → Inspect (or F12)
2. Check applied styles in the Styles panel
3. Look for crossed-out styles (overridden)

```html
<!-- Example to inspect -->
<button class="bg-blue-500 p-4 text-white hover:bg-blue-700">
  Debug Me
</button>
```

### Computed Tab
Use the Computed tab to see final applied CSS values:
1. Select element in Elements panel
2. Click "Computed" tab
3. Search for specific properties

## Common Issues & Solutions

### 1. Classes Not Applied

**Problem:** Tailwind classes have no visible effect

**Solutions:**

#### Check for typos
```html
<!-- Wrong -->
<div class="text-centre">Won't work</div>

<!-- Correct -->
<div class="text-center">Will work</div>
```

#### Verify PurgeCSS configuration
```js
// tailwind.config.js
module.exports = {
  content: [
    // Include ALL template files
    './src/**/*.{html,js,jsx,ts,tsx}'
  ],
  // other config
}
```

#### Check CSS loading order
```html
<!-- Correct order -->
<link rel="stylesheet" href="base.css">
<link rel="stylesheet" href="tailwind.css">
<link rel="stylesheet" href="custom.css">
```

### 2. Layout Problems

**Problem:** Elements not positioned correctly

**Solutions:**

#### Visualize containers
```html
<div class="flex items-center" style="outline: 1px solid red">
  <div style="outline: 1px solid blue">Item 1</div>
  <div style="outline: 1px solid green">Item 2</div>
</div>
```

#### Check parent height for percentage heights
```html
<!-- This won't work as expected -->
<div class="h-full">I won't be full height</div>

<!-- This will work -->
<div class="h-screen">
  <div class="h-full">Now I'll be full height</div>
</div>
```

#### Verify responsive prefixes
```html
<!-- Always a column -->
<div class="flex-col">...</div>

<!-- Column on mobile, row on medium screens -->
<div class="flex flex-col md:flex-row">...</div>
```

### 3. Conflicting Classes

**Problem:** Classes override each other unexpectedly

**Solutions:**

#### Check specificity and order
The last conflicting class wins:
```html
<!-- This will be blue -->
<div class="text-red-500 text-blue-500">Blue text</div>
```

#### Avoid conflicting utilities
```html
<!-- Conflicting padding -->
<div class="p-4 px-2">Confusing result</div>

<!-- Better approach -->
<div class="py-4 px-2">Clear intent</div>
```

## Debugging Tools

### 1. Temporary Debug Classes

Add to your CSS or component:
```css
.debug-borders * { outline: 1px solid red; }
.debug-grid { background: repeating-linear-gradient(to right, rgba(0,0,0,0.1), rgba(0,0,0,0.1) 1px, transparent 1px, transparent 20px); }
```

### 2. Console Logging Dynamic Classes

```jsx
// React example
const classes = `flex ${isMobile ? 'flex-col' : 'flex-row'}`;
console.log('Applied classes:', classes);
```

### 3. VS Code Extensions

- **Tailwind CSS IntelliSense**: Auto-completion and linting
- **Headwind**: Class sorter for consistent ordering

## Testing Configuration

### Add a Test Color

To verify your config is loaded:

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        'test-pink': '#ff00ff'
      }
    }
  }
}
```

Then use in HTML:
```html
<div class="text-test-pink">
  If this is bright pink, config is working
</div>
```

## Performance Issues

### Large CSS Bundle

Check CSS file size:
```bash
ls -la public/css/tailwind.css
```

If over 100KB in production, PurgeCSS may not be configured correctly.

### Fix: Enable JIT Mode

```js
// tailwind.config.js (v2.x)
module.exports = {
  mode: 'jit',
  // In v3.x, JIT is on by default
  // other config
}
```

## Debugging Checklist

When troubleshooting:

1. ✅ Verify correct class names (no typos)
2. ✅ Check for conflicting classes
3. ✅ Inspect CSS application in DevTools
4. ✅ Test responsive behavior at different widths
5. ✅ Verify Tailwind config is loaded correctly
6. ✅ Check for console errors

## Getting Community Help

If stuck, try:
- Official Tailwind CSS Discord
- Stack Overflow with the [tailwindcss] tag
- GitHub issues for potential bugs 