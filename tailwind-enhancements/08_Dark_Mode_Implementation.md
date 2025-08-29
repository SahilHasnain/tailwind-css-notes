# Dark Mode Implementation with Tailwind CSS

This guide covers strategies for implementing dark mode in Tailwind CSS projects.

## Configuration

```js
// tailwind.config.js
module.exports = {
  darkMode: 'media', // System preference (default)
  // OR
  darkMode: 'class', // Manual toggle with a 'dark' class
}
```

## Basic Usage

```html
<div class="bg-white dark:bg-gray-800 text-black dark:text-white">
  This text adapts to dark mode
</div>
```

## Toggle Implementation

```html
<button id="toggle">Toggle Dark Mode</button>

<script>
  const toggle = document.getElementById('toggle');
  
  // Check saved theme or system preference
  const isDark = localStorage.theme === 'dark' || 
    (!localStorage.theme && window.matchMedia('(prefers-color-scheme: dark)').matches);
  
  if (isDark) document.documentElement.classList.add('dark');
  
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

## Color Recommendations

| Light Mode | Dark Mode | Use |
|------------|-----------|-----|
| white | gray-900 | Background |
| gray-100 | gray-800 | Card bg |
| gray-800 | gray-200 | Text |
| blue-600 | blue-400 | Accent |

## Best Practices

1. **Prevent flash of wrong theme**
   ```html
   <script>
     // In <head>
     if (localStorage.theme === 'dark' || (!localStorage.theme && 
       window.matchMedia('(prefers-color-scheme: dark)').matches)) {
       document.documentElement.classList.add('dark');
     }
   </script>
   ```

2. **Handle images**
   ```html
   <img src="/logo-light.png" class="block dark:hidden" alt="Logo" />
   <img src="/logo-dark.png" class="hidden dark:block" alt="Logo" />
   ```

3. **Smooth transitions**
   ```css
   html { transition: background-color 0.3s ease; }
   ``` 