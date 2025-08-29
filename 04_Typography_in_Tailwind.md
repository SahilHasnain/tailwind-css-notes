# Typography Utilities in Tailwind CSS

Typography utilities help you control text-related styling in your project. This includes text size, color, weight, spacing, alignment, etc.

## 1. Text Size (Font Size)
Tailwind provides predefined classes for text sizes:

| Class | Size |
|-------|------|
| `text-xs` | Extra Small (0.75rem) |
| `text-sm` | Small (0.875rem) |
| `text-base` | Normal (1rem - default) |
| `text-lg` | Large (1.125rem) |
| `text-xl` | Extra Large (1.25rem) |
| `text-2xl` | 2x Large (1.5rem) |
| `text-3xl` | 3x Large (1.875rem) |
| `text-4xl` | 4x Large (2.25rem) |
| `text-5xl` | 5x Large (3rem) |
| `text-6xl` | 6x Large (3.75rem) |

**Example:**
```html
<p class="text-2xl">Yeh bada text hai</p>
<p class="text-sm">Yeh chhota text hai</p>
```

## 2. Text Color
Format: `text-{color}-{number}`

**Example:**
```html
<p class="text-red-500">Yeh lal text hai</p>
<p class="text-green-600">Yeh hara text hai</p>
<p class="text-gray-700">Yeh gray text hai</p>
```

## 3. Font Weight
Control how bold or light text appears:

| Class | Meaning | Weight Value |
|-------|---------|-------------|
| `font-thin` | Bahut patla | 100 |
| `font-extralight` | Extra patla | 200 |
| `font-light` | Halka | 300 |
| `font-normal` | Default weight | 400 |
| `font-medium` | Medium bold | 500 |
| `font-semibold` | Semi bold | 600 |
| `font-bold` | Bold | 700 |
| `font-extrabold` | Extra bold | 800 |
| `font-black` | Bahut bold | 900 |

**Example:**
```html
<p class="font-bold">Yeh bold text hai</p>
<p class="font-light">Yeh light text hai</p>
```

## 4. Text Alignment
Control text alignment horizontally:

| Class | Effect |
|-------|--------|
| `text-left` | Left alignment (default) |
| `text-center` | Center alignment |
| `text-right` | Right alignment |
| `text-justify` | Justify text (equal width lines) |

**Example:**
```html
<p class="text-center">Yeh center aligned text hai</p>
<p class="text-right">Yeh right aligned text hai</p>
```

## 5. Letter Spacing (Tracking)
Control space between letters:

| Class | Effect |
|-------|--------|
| `tracking-tighter` | Letters pass-pass (-0.05em) |
| `tracking-tight` | Tight spacing (-0.025em) |
| `tracking-normal` | Default spacing (0em) |
| `tracking-wide` | Letters ke beech gap zyada (0.025em) |
| `tracking-wider` | More gap (0.05em) |
| `tracking-widest` | Sabse zyada gap (0.1em) |

**Example:**
```html
<p class="tracking-widest">W I D E   T E X T</p>
<p class="tracking-tight">Tight text letters pass-pass</p>
```

## 6. Line Height (Leading)
Control vertical spacing between lines:

| Class | Effect |
|-------|--------|
| `leading-none` | Line spacing bahut kam (1) |
| `leading-tight` | Line spacing kam (1.25) |
| `leading-snug` | Compact spacing (1.375) |
| `leading-normal` | Default spacing (1.5) |
| `leading-relaxed` | Increased spacing (1.625) |
| `leading-loose` | Line spacing zyada (2) |

**Example:**
```html
<p class="leading-loose">
  Line 1<br>
  Line 2<br>
  Line 3
</p>
<p class="leading-tight">
  Line 1<br>
  Line 2<br>
  Line 3
</p>
```

## 7. Text Decoration
Add underlines or strikethroughs:

| Class | Effect |
|-------|--------|
| `underline` | Underlined text |
| `line-through` | Strike-through text |
| `no-underline` | Removes underline |

## 8. Text Transform
Change case of text:

| Class | Effect |
|-------|--------|
| `uppercase` | ALL CAPITAL LETTERS |
| `lowercase` | all small letters |
| `capitalize` | First Letter Of Each Word Capital |
| `normal-case` | Normal text case |

## Typography Practice Component

Yeh component Tailwind ki text utilities ka use karta hai:

```html
<div class="p-6 max-w-lg mx-auto bg-white rounded-xl shadow-md space-y-4">
  <h1 class="text-4xl font-bold text-center text-blue-700">Tailwind Typography</h1>
  <p class="text-base text-gray-700 leading-relaxed">
    Tailwind CSS allows you to rapidly build modern websites without ever leaving your HTML.
  </p>
  <p class="text-sm text-gray-500 tracking-wide text-right">
    — By You
  </p>
</div>
```

## Practice Suggestions
- Har typography class ka 1 example banao apne HTML me.
- Mix karo font-size + font-weight + color + alignment
- Khud se ek "About Me" section banao Tailwind use karke. 