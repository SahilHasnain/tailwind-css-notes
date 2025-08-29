# Responsive Design in Tailwind CSS

Tailwind CSS ka sabse powerful feature hai iska mobile-first responsive system. Is section me hum seekhenge kaise har screen size ke liye alag-alag styling apply karte hain.

## Tailwind ke Default Breakpoints

| Breakpoint | Width | Usage |
|------------|-------|-------|
| (default) | < 640px | Mobile screens |
| `sm:` | ≥ 640px | Small devices |
| `md:` | ≥ 768px | Medium devices (tablets) |
| `lg:` | ≥ 1024px | Large devices (laptops) |
| `xl:` | ≥ 1280px | Extra large (desktops) |
| `2xl:` | ≥ 1536px | Very large screens |

## Responsive Design Syntax

Tailwind ke responsive design ka syntax hai:

```
{breakpoint}:{utility}
```

Example:
```html
<p class="text-sm md:text-lg lg:text-xl">
  Responsive Text
</p>
```

Meaning:
- By default (mobile): `text-sm`
- On medium screens (`md`): `text-lg`
- On large screens (`lg`): `text-xl`

## Mobile-First Approach

Tailwind responsive classes follow a mobile-first approach. Matlab:

1. Default styles mobile ke liye hote hain
2. Jab screen size breakpoint ko cross karti hai, tabhi naya style apply hota hai
3. Har larger breakpoint automatically smaller breakpoints ke styles ko override karta hai

## Responsive Example: Layout Change

```html
<div class="flex flex-col md:flex-row">
  <div class="bg-red-300 p-4">
    Box 1
  </div>
  <div class="bg-blue-300 p-4">
    Box 2
  </div>
</div>
```

Effect:
- Mobile screens: Boxes vertically stacked (flex-col)
- md screens and above: Boxes horizontally side by side (flex-row)

## Responsive Example: Grid Columns

```html
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
  <div class="bg-blue-100 p-4 rounded shadow">Card 1</div>
  <div class="bg-green-100 p-4 rounded shadow">Card 2</div>
  <div class="bg-pink-100 p-4 rounded shadow">Card 3</div>
</div>
```

Effect:
- Mobile: 1 column
- Tablet: 2 columns
- Desktop: 3 columns

## Responsive Text Size

```html
<h1 class="text-xl sm:text-2xl md:text-3xl lg:text-4xl font-bold">
  Responsive Heading
</h1>
```

Effect:
- Text size increases as screen size increases

## Responsive Visibility (Hide/Show Elements)

```html
<p class="block sm:hidden">
  This text only shows on mobile screens
</p>

<p class="hidden sm:block">
  This text only shows on larger screens
</p>
```

Combinations:
- `hidden` + `md:block`: Hide on small screens, show on medium and up
- `block` + `lg:hidden`: Show on all screens except large and up

## Responsive Padding and Margin

```html
<div class="p-2 md:p-4 lg:p-8">
  Padding increases as screen size increases
</div>
```

## Complete Example: Responsive Header

```html
<header class="bg-white shadow">
  <!-- Mobile View -->
  <div class="flex justify-between items-center p-4 md:hidden">
    <h1 class="text-xl font-bold">Mobile Logo</h1>
    <button class="bg-gray-200 p-2 rounded">
      Menu
    </button>
  </div>
  
  <!-- Desktop View -->
  <div class="hidden md:flex md:justify-between md:items-center md:p-6">
    <h1 class="text-2xl font-bold">Desktop Logo</h1>
    <nav class="flex gap-6">
      <a href="#" class="text-gray-600 hover:text-blue-500">Home</a>
      <a href="#" class="text-gray-600 hover:text-blue-500">About</a>
      <a href="#" class="text-gray-600 hover:text-blue-500">Services</a>
      <a href="#" class="text-gray-600 hover:text-blue-500">Contact</a>
    </nav>
  </div>
</header>
```

## Responsive Utility Classes

Tailwind me koi bhi utility class responsive bana sakti hai:

- `sm:px-4` (Padding horizontal on small screens and up)
- `md:grid-cols-2` (2 columns on medium screens and up)
- `lg:justify-center` (Center horizontally on large screens and up)
- `xl:rounded-xl` (Extra large rounded corners on xl screens)

## Practice Example: Responsive Card Layout

```html
<div class="p-4">
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
    <div class="bg-white p-4 rounded shadow-md">
      <h2 class="text-lg sm:text-xl lg:text-2xl font-bold">Card Title</h2>
      <p class="text-sm sm:text-base">This is a responsive card that changes based on screen size.</p>
    </div>
    <div class="bg-white p-4 rounded shadow-md">
      <h2 class="text-lg sm:text-xl lg:text-2xl font-bold">Card Title</h2>
      <p class="text-sm sm:text-base">Styles change at breakpoints.</p>
    </div>
    <div class="bg-white p-4 rounded shadow-md">
      <h2 class="text-lg sm:text-xl lg:text-2xl font-bold">Card Title</h2>
      <p class="text-sm sm:text-base">Tailwind makes responsive design easy!</p>
    </div>
  </div>
</div>
```

## Practice Tasks

1. Create a responsive navbar that shows links horizontally on desktop but shows a menu button on mobile
2. Create a page with sidebar that appears side-by-side on desktop but stacks on mobile
3. Create responsive text that gets larger on bigger screens
4. Hide certain elements on mobile but show them on desktop 