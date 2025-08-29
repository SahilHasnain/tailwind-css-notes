# Tailwind CSS Syntax and Classes

Tailwind CSS ka style system utility-first hota hai — matlab har kaam ke liye ek chhoti class hoti hai. Tailwind CSS classes ka format aur usage samajhna bahut zaroori hai.

## Common Syntax Format

Tailwind me classes usually is format me likhi jati hain:
```propertyName-value
```

### Examples:

| Class | Matlab |
|-------|--------|
| `bg-red-500` | Background color red (shade 500) |
| `text-xl` | Font size: Extra Large |
| `p-4` | Padding: 1rem (around all sides) |
| `px-4` | Horizontal Padding (left + right) |
| `py-2` | Vertical Padding (top + bottom) |
| `m-2` | Margin: 0.5rem |
| `rounded-lg` | Border radius: large |
| `shadow-md` | Medium shadow |

## Detailed Explanation of Key Classes

### `p-4` (Padding)
1. **Kya ho raha hai?**
   `p-4` ek utility class hai Tailwind ki, jo element ke chaaron taraf equal padding lagati hai.

2. **Kyun use karte hain?**
   Padding ka matlab hota hai content aur border ke beech ka space. Isse tumhara content thoda breathable aur visually balanced lagta hai.

3. **Kaise kaam karta hai?**
   Tailwind me `p-4` ka matlab hota hai:
   ```css
   padding: 1rem;  /* 1 rem = 16px by default */
   ```

4. **Har part ka Matlab**
   - `p` = padding (sab sides: top, right, bottom, left)
   - `-4` = Tailwind ka spacing scale ka 4th step → 1 rem (yaani 16px)

5. **Tailwind ka spacing scale:**
   | Class | Value |
   |-------|-------|
   | 0 | 0px |
   | 1 | 0.25rem (4px) |
   | 2 | 0.5rem (8px) |
   | 3 | 0.75rem (12px) |
   | 4 | 1rem (16px) |
   | 5 | 1.25rem (20px) |
   | 6 | 1.5rem (24px) |

6. **Common Confusions:**
   | Confusion | Clarification |
   |-----------|---------------|
   | p-4 vs m-4 | p-4 is inside the box (padding), m-4 is outside (margin) |
   | py-4 vs px-4 | py = vertical padding (top+bottom), px = horizontal (left+right) |

7. **Real-Life Usage:**
   - Jab tum ek button banao, to `p-2` ya `p-3` use karte ho to usme thoda sa andar ka space aaye
   - Ek card component ke andar content ko breathable banane ke liye `p-6` lagate hain

### `bg-blue-500` (Background)
1. **Kya ho raha hai?**
   Ye ek background color lagane wali class hai — specifically Tailwind ke blue color ke shade 500 ka.

2. **Kyun use karte hain?**
   Background color elements ko visually alag banata hai. Blue color ka use emphasis aur trust dikhata hai.

3. **Kaise kaam karta hai?**
   Tailwind me predefined color shades hote hain jaise:
   ```css
   .bg-blue-500 {
     background-color: #3B82F6;
   }
   ```

4. **Har part ka matlab**
   - `bg` = Background
   - `blue` = Color name
   - `500` = Intensity level (darker = 900, lighter = 100)

5. **Common Mistakes:**
   - `bg-blue` likhna galat hai — tumhe intensity bhi likhni hoti hai
   - Dark ya light shades ko soch samajh ke select karo based on context

6. **Real-Life Usage:**
   - Primary buttons: `bg-blue-500`
   - Alert boxes: `bg-yellow-200`, `bg-red-500`
   - Cards: `bg-white` or `bg-gray-100`

## Example HTML Code

```html
<div class="bg-blue-100 p-6 rounded-lg shadow-md">
  <h2 class="text-2xl font-bold text-gray-700">Welcome!</h2>
  <p class="text-sm text-gray-600">Yeh Tailwind ka example hai</p>
</div>
```

## Tailwind ki Classes ke Main Categories

| Category | Examples |
|----------|----------|
| Colors | text-red-500, bg-green-200 |
| Spacing (Padding/Margin) | p-4, m-2, pt-3, mx-5 |
| Typography | text-lg, font-bold, uppercase |
| Layout | flex, grid, justify-between |
| Borders | border, border-gray-300, rounded-xl |
| Effects | shadow-lg, opacity-50, hover:bg-blue-400 |
| Responsive | md:text-xl, lg:p-8 |

## Responsive Syntax Example

```html
<p class="text-sm md:text-lg lg:text-xl">
  Hello Responsive World
</p>
```

Matlab:
- Small screen pe: text-sm
- Medium screen (tablet) pe: text-lg
- Large screen (laptop) pe: text-xl 