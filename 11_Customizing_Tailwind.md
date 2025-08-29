# Customizing Tailwind CSS Using Configuration

Tailwind CSS ki built-in settings ko override karke apna custom design system create karna ek powerful feature hai. This allows you to define your own colors, spacing, fonts, and other design tokens.

## Why Customize Tailwind?

- Brand colors add karne ke liye
- Custom font families use karne ke liye
- Special spacing values create karne ke liye
- Extra utilities add karne ke liye

## Using tailwind.config.js

Jab aap NPM ke through Tailwind install karte hain, to `tailwind.config.js` file automatically create hoti hai. Is file me aap Tailwind ki configuration customize kar sakte hain.

### Basic Configuration Structure

```js
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {
      colors: {
        // Your custom colors
      },
      spacing: {
        // Your custom spacing
      },
      fontFamily: {
        // Your custom fonts
      }
    }
  },
  plugins: []
}
```

## Customizing with CDN Version (Inline Configuration)

CDN version me bhi customization possible hai with inline configuration:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Tailwind CDN Customization</title>
  
  <!-- Inline Tailwind Configuration -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            primary: '#1fb6ff',
            secondary: '#ff49db'
          },
          spacing: {
            '72': '18rem',
            '84': '21rem',
            '96': '24rem'
          },
          fontFamily: {
            poppins: ['Poppins', 'sans-serif']
          }
        }
      }
    }
  </script>
  
  <!-- Load Tailwind via CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body>
  <!-- Your HTML here -->
</body>
</html>
```

## Customizing Colors

Colors customize karne se aap apne brand colors use kar sakte hain:

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: '#1fb6ff',
        secondary: '#ff49db',
        danger: '#ff5252',
        success: '#47d78a',
        warning: '#ffc82c'
      }
    }
  }
}
```

Ab aap `bg-primary`, `text-secondary`, `border-danger` jaise classes use kar sakte hain.

## Customizing Spacing

Spacing values add karne ke liye:

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      spacing: {
        '72': '18rem',
        '84': '21rem',
        '96': '24rem',
        '128': '32rem'
      }
    }
  }
}
```

Ab aap `p-72`, `mt-84`, `h-96`, `w-128` jaise classes use kar sakte hain.

## Customizing Fonts

Font families add karne ke liye:

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      fontFamily: {
        poppins: ['Poppins', 'sans-serif'],
        montserrat: ['Montserrat', 'sans-serif']
      }
    }
  }
}
```

Ab aap `font-poppins` aur `font-montserrat` classes use kar sakte hain.

## Full Custom Configuration Example

```js
// tailwind.config.js
module.exports = {
  content: ["./index.html"],
  theme: {
    extend: {
      colors: {
        primary: {
          DEFAULT: '#3490dc',
          light: '#93C5FD',
          dark: '#1E40AF'
        },
        secondary: '#ff49db'
      },
      spacing: {
        '72': '18rem',
        '84': '21rem',
        '96': '24rem'
      },
      fontFamily: {
        poppins: ['Poppins', 'sans-serif']
      }
    }
  },
  plugins: []
}
```

## Using Custom Classes in HTML

```html
<div class="bg-primary text-white font-poppins min-h-screen flex items-center justify-center">
  <div class="bg-white text-gray-800 p-10 rounded shadow-lg w-96 space-y-4">
    <h1 class="text-3xl font-bold text-secondary">Tailwind Customization</h1>
    <p class="text-lg">
      This project uses custom colors, spacing and fonts via Tailwind config.
    </p>
    <div class="bg-primary h-72 w-full rounded-lg"></div>
  </div>
</div>
```

## Best Practices for Customization

1. **Use `extend` instead of replacing**:
   - `extend` keeps default utilities and adds yours
   - Direct replacement can remove useful defaults

2. **Maintain scale consistency**:
   - Match the existing scales when adding values
   - Example: if spacing goes 4, 8, 16, 24, keep that pattern

3. **Document your customizations**:
   - Add comments explaining brand colors or special values
   - Makes it easier for team members to understand

4. **Keep in theme section**:
   - All design token customizations go in the `theme` section
   - Plugin customizations are separate

## Example Project Link in HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Tailwind NPM Custom</title>
  <link href="./dist/output.css" rel="stylesheet" />
</head>
<body class="bg-primary text-white font-poppins min-h-screen flex items-center justify-center">
  <div class="bg-white text-dark p-10 rounded shadow-lg w-96 space-y-4">
    <h1 class="text-3xl font-bold text-secondary">Tailwind Customization</h1>
    <p class="text-lg">
      This project uses custom colors, spacing and fonts via Tailwind config.
    </p>
    <div class="bg-primary h-72 w-full rounded-lg"></div>
  </div>
</body>
</html>
```

To implement these customizations, remember to run Tailwind CLI with the watch flag to rebuild CSS when configuration changes:

```bash
npx tailwindcss -i ./styles/input.css -o ./dist/output.css --watch
``` 