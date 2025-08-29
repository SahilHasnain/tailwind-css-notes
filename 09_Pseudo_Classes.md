# Pseudo Classes in Tailwind CSS

Tailwind CSS me pseudo-classes ko prefix ki tarah use kiya jata hai. Ye UI elements ko interactive banane ke liye essential hote hain, jaise hover effects, focus states, active states, etc.

## Common Pseudo-Classes

Tailwind CSS following pseudo-classes support karta hai:

| Prefix | Description |
|--------|-------------|
| `hover:` | Mouse hover kar rahe ho |
| `focus:` | Element focused hai (e.g., clicked input) |
| `active:` | Element clicked/pressed hai |
| `disabled:` | Disabled element ke liye |
| `visited:` | Visited links ke liye |
| `first:` | First child element |
| `last:` | Last child element |
| `odd:` | Odd-numbered children |
| `even:` | Even-numbered children |
| `group-hover:` | Parent element hover hone par child elements |

## 1. Hover State

Element par mouse hover karne par style change karna:

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
  Hover me
</button>
```

Explanation:
- Normal state: `bg-blue-500` (blue background)
- Hover state: `hover:bg-blue-700` (darker blue background)

## 2. Focus State

Jab user input element par click kare ya keyboard navigation se focus kare:

```html
<input type="text" class="border-2 border-gray-300 focus:border-blue-500 outline-none p-2 rounded" placeholder="Focus karo mujhe">
```

Explanation:
- Normal state: `border-gray-300` (gray border)
- Focus state: `focus:border-blue-500` (blue border when focused)

## 3. Active State

Jab element par click ho raha ho (button pressed):

```html
<button class="bg-green-500 active:bg-green-700 text-white py-2 px-4 rounded">
  Active button
</button>
```

Explanation:
- Normal state: `bg-green-500`
- Active state (pressed): `active:bg-green-700`

## 4. Group Hover (Parent Hover Affecting Children)

Parent element hover hone par child elements ka style change karna:

```html
<div class="group p-4 bg-gray-100 hover:bg-gray-200">
  <h2 class="text-lg font-bold group-hover:text-blue-600">Group Hover Title</h2>
  <p class="text-gray-500 group-hover:text-black">Yeh bhi hover par change hota hai</p>
</div>
```

Explanation:
- Parent ko `.group` class deni padti hai
- Child elements par `group-hover:` prefix lagate hain
- Jab parent hover hoga, tab child elements ke styles apply honge

## 5. Disabled State

Disabled elements ke liye special styling:

```html
<button class="bg-blue-500 text-white py-2 px-4 rounded disabled:bg-gray-400 disabled:cursor-not-allowed" disabled>
  Disabled Button
</button>
```

## 6. Focus-Within

Container ke andar koi bhi element focus hone par styling:

```html
<div class="focus-within:ring-2 ring-blue-400 p-4 rounded border">
  <label class="block mb-2">Email</label>
  <input type="email" class="p-2 border rounded w-full">
</div>
```

## 7. Transitions (Smooth Animation)

Hover, focus, active states ke liye smooth transition add karna:

```html
<button class="bg-purple-500 hover:bg-purple-700 text-white py-2 px-4 rounded transition duration-300">
  Smooth Hover
</button>
```

Explanation:
- `transition`: Basic transition effect enable karta hai
- `duration-300`: 300ms transition time
- `ease-in-out`: Smooth acceleration curve (optional)

## Complete Example: Interactive Card with Pseudo-Classes

```html
<div class="max-w-sm mx-auto mt-10">
  <div class="bg-white shadow-md rounded-lg overflow-hidden transform hover:scale-105 transition duration-300">
    <img src="https://via.placeholder.com/400x200" alt="Card Image" class="w-full h-48 object-cover">
    
    <div class="p-6">
      <h2 class="text-xl font-bold text-gray-800 hover:text-blue-600 transition">Interactive Card</h2>
      <p class="mt-2 text-gray-600">This card has hover effects and transitions.</p>

      <div class="mt-4 flex gap-2">
        <button class="bg-blue-500 hover:bg-blue-700 active:bg-blue-800 focus:outline-none focus:ring-2 focus:ring-blue-300 text-white px-4 py-2 rounded transition">
          Primary
        </button>
        <button class="bg-gray-200 hover:bg-gray-300 active:bg-gray-400 text-gray-800 px-4 py-2 rounded transition">
          Secondary
        </button>
      </div>
    </div>
  </div>
</div>
```

## Summary Table

| Scenario | Class Example | Effect |
|----------|---------------|--------|
| Hover | `hover:bg-blue-700` | Mouse hover par background change |
| Focus | `focus:ring-2` | Click ya tab key focus pe ring effect |
| Active | `active:scale-95` | Click karte time scale down |
| Group Hover | `group-hover:text-blue-500` | Parent hover pe child text color |
| Transition | `transition duration-300` | Smooth 300ms animation |

## Practice Tasks

1. Create a button with hover, focus, and active states
2. Create a card that grows slightly on hover
3. Create a group of elements where child elements change when hovering on parent
4. Create an input field that changes border color on focus 