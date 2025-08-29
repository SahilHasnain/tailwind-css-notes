# Tailwind CSS Cheat Sheets

Quick reference guides for Tailwind CSS utilities, organized by category for easy lookup during development.

## Layout Cheat Sheet

### Container
```
container               Set width to current breakpoint
mx-auto                 Center container
```

### Display
```
block                   display: block
inline-block            display: inline-block
inline                  display: inline
flex                    display: flex
inline-flex             display: inline-flex
grid                    display: grid
inline-grid             display: inline-grid
hidden                  display: none
```

### Overflow
```
overflow-auto           overflow: auto
overflow-hidden         overflow: hidden
overflow-visible        overflow: visible
overflow-scroll         overflow: scroll
overflow-x-scroll       overflow-x: scroll
overflow-y-scroll       overflow-y: scroll
```

### Position
```
static                  position: static
fixed                   position: fixed
absolute                position: absolute
relative                position: relative
sticky                  position: sticky
```

### Top/Right/Bottom/Left
```
top-0                   top: 0
right-0                 right: 0
bottom-0                bottom: 0
left-0                  left: 0
inset-0                 top, right, bottom, left: 0
```

## Flexbox Cheat Sheet

### Flex Direction
```
flex-row                flex-direction: row
flex-row-reverse        flex-direction: row-reverse
flex-col                flex-direction: column
flex-col-reverse        flex-direction: column-reverse
```

### Flex Wrap
```
flex-wrap               flex-wrap: wrap
flex-wrap-reverse       flex-wrap: wrap-reverse
flex-nowrap             flex-wrap: nowrap
```

### Justify Content
```
justify-start           justify-content: flex-start
justify-center          justify-content: center
justify-end             justify-content: flex-end
justify-between         justify-content: space-between
justify-around          justify-content: space-around
justify-evenly          justify-content: space-evenly
```

### Align Items
```
items-start             align-items: flex-start
items-center            align-items: center
items-end               align-items: flex-end
items-baseline          align-items: baseline
items-stretch           align-items: stretch
```

### Align Content
```
content-start           align-content: flex-start
content-center          align-content: center
content-end             align-content: flex-end
content-between         align-content: space-between
content-around          align-content: space-around
content-evenly          align-content: space-evenly
```

### Flex Item Properties
```
flex-1                  flex: 1 1 0%
flex-auto               flex: 1 1 auto
flex-initial            flex: 0 1 auto
flex-none               flex: none
grow                    flex-grow: 1
grow-0                  flex-grow: 0
shrink                  flex-shrink: 1
shrink-0                flex-shrink: 0
```

## Grid Cheat Sheet

### Grid Template Columns
```
grid-cols-1             grid-template-columns: repeat(1, minmax(0, 1fr))
grid-cols-2             grid-template-columns: repeat(2, minmax(0, 1fr))
grid-cols-3             grid-template-columns: repeat(3, minmax(0, 1fr))
grid-cols-4             grid-template-columns: repeat(4, minmax(0, 1fr))
grid-cols-5             grid-template-columns: repeat(5, minmax(0, 1fr))
grid-cols-6             grid-template-columns: repeat(6, minmax(0, 1fr))
grid-cols-12            grid-template-columns: repeat(12, minmax(0, 1fr))
grid-cols-none          grid-template-columns: none
```

### Grid Column Start/End
```
col-auto                grid-column: auto
col-span-1              grid-column: span 1 / span 1
col-span-2              grid-column: span 2 / span 2
col-span-3              grid-column: span 3 / span 3
col-start-1             grid-column-start: 1
col-start-2             grid-column-start: 2
col-end-3               grid-column-end: 3
col-end-4               grid-column-end: 4
```

### Grid Template Rows
```
grid-rows-1             grid-template-rows: repeat(1, minmax(0, 1fr))
grid-rows-2             grid-template-rows: repeat(2, minmax(0, 1fr))
grid-rows-3             grid-template-rows: repeat(3, minmax(0, 1fr))
grid-rows-none          grid-template-rows: none
```

### Grid Row Start/End
```
row-auto                grid-row: auto
row-span-1              grid-row: span 1 / span 1
row-span-2              grid-row: span 2 / span 2
row-span-3              grid-row: span 3 / span 3
row-start-1             grid-row-start: 1
row-start-2             grid-row-start: 2
row-end-3               grid-row-end: 3
row-end-4               grid-row-end: 4
```

### Grid Auto Flow
```
grid-flow-row           grid-auto-flow: row
grid-flow-col           grid-auto-flow: column
grid-flow-row-dense     grid-auto-flow: row dense
grid-flow-col-dense     grid-auto-flow: column dense
```

### Gap
```
gap-0                   gap: 0
gap-1                   gap: 0.25rem
gap-2                   gap: 0.5rem
gap-4                   gap: 1rem
gap-x-4                 column-gap: 1rem
gap-y-4                 row-gap: 1rem
```

## Spacing Cheat Sheet

### Padding
```
p-0                     padding: 0
p-1                     padding: 0.25rem
p-2                     padding: 0.5rem
p-4                     padding: 1rem
p-8                     padding: 2rem
px-4                    padding-left: 1rem; padding-right: 1rem
py-4                    padding-top: 1rem; padding-bottom: 1rem
pt-4                    padding-top: 1rem
pr-4                    padding-right: 1rem
pb-4                    padding-bottom: 1rem
pl-4                    padding-left: 1rem
```

### Margin
```
m-0                     margin: 0
m-1                     margin: 0.25rem
m-2                     margin: 0.5rem
m-4                     margin: 1rem
m-8                     margin: 2rem
mx-4                    margin-left: 1rem; margin-right: 1rem
my-4                    margin-top: 1rem; margin-bottom: 1rem
mt-4                    margin-top: 1rem
mr-4                    margin-right: 1rem
mb-4                    margin-bottom: 1rem
ml-4                    margin-left: 1rem
-m-4                    margin: -1rem
mx-auto                 margin-left: auto; margin-right: auto
```

### Space Between
```
space-x-4               margin-left on all children except first
space-y-4               margin-top on all children except first
space-x-reverse         reverse space-x direction
space-y-reverse         reverse space-y direction
```

## Typography Cheat Sheet

### Font Family
```
font-sans                font-family: system-ui, sans-serif
font-serif               font-family: Georgia, serif
font-mono                font-family: monospace
```

### Font Size
```
text-xs                 font-size: 0.75rem
text-sm                 font-size: 0.875rem
text-base               font-size: 1rem
text-lg                 font-size: 1.125rem
text-xl                 font-size: 1.25rem
text-2xl                font-size: 1.5rem
text-3xl                font-size: 1.875rem
text-4xl                font-size: 2.25rem
text-5xl                font-size: 3rem
text-6xl                font-size: 3.75rem
```

### Font Weight
```
font-thin               font-weight: 100
font-extralight         font-weight: 200
font-light              font-weight: 300
font-normal             font-weight: 400
font-medium             font-weight: 500
font-semibold           font-weight: 600
font-bold               font-weight: 700
font-extrabold          font-weight: 800
font-black              font-weight: 900
```

### Text Alignment
```
text-left               text-align: left
text-center             text-align: center
text-right              text-align: right
text-justify            text-align: justify
```

### Text Color
```
text-{color}-{shade}    color: {value}
text-transparent         color: transparent
text-current             color: currentColor
text-black               color: #000
text-white               color: #fff
text-red-500             color: #ef4444
text-blue-500            color: #3b82f6
```

### Text Decoration
```
underline               text-decoration: underline
line-through            text-decoration: line-through
no-underline            text-decoration: none
```

### Text Transform
```
uppercase               text-transform: uppercase
lowercase               text-transform: lowercase
capitalize              text-transform: capitalize
normal-case             text-transform: none
```

### Letter Spacing
```
tracking-tighter        letter-spacing: -0.05em
tracking-tight          letter-spacing: -0.025em
tracking-normal         letter-spacing: 0
tracking-wide           letter-spacing: 0.025em
tracking-wider          letter-spacing: 0.05em
tracking-widest         letter-spacing: 0.1em
```

### Line Height
```
leading-none            line-height: 1
leading-tight           line-height: 1.25
leading-snug            line-height: 1.375
leading-normal          line-height: 1.5
leading-relaxed         line-height: 1.625
leading-loose           line-height: 2
```

## Background & Borders Cheat Sheet

### Background Color
```
bg-{color}-{shade}      background-color: {value}
bg-transparent          background-color: transparent
bg-current              background-color: currentColor
bg-black                background-color: #000
bg-white                background-color: #fff
bg-red-500              background-color: #ef4444
bg-blue-500             background-color: #3b82f6
```

### Background Opacity
```
bg-opacity-0            --tw-bg-opacity: 0
bg-opacity-50           --tw-bg-opacity: 0.5
bg-opacity-100          --tw-bg-opacity: 1
```

### Border Width
```
border                  border-width: 1px
border-0                border-width: 0
border-2                border-width: 2px
border-4                border-width: 4px
border-8                border-width: 8px
border-t                border-top-width: 1px
border-r                border-right-width: 1px
border-b                border-bottom-width: 1px
border-l                border-left-width: 1px
```

### Border Color
```
border-{color}-{shade}  border-color: {value}
border-transparent      border-color: transparent
border-current          border-color: currentColor
border-black            border-color: #000
border-white            border-color: #fff
border-red-500          border-color: #ef4444
border-blue-500         border-color: #3b82f6
```

### Border Radius
```
rounded-none            border-radius: 0
rounded-sm              border-radius: 0.125rem
rounded                 border-radius: 0.25rem
rounded-md              border-radius: 0.375rem
rounded-lg              border-radius: 0.5rem
rounded-xl              border-radius: 0.75rem
rounded-2xl             border-radius: 1rem
rounded-3xl             border-radius: 1.5rem
rounded-full            border-radius: 9999px
```

## Effects Cheat Sheet

### Shadow
```
shadow-sm               box-shadow: 0 1px 2px 0 rgb(0 0 0 / 0.05)
shadow                  box-shadow: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1)
shadow-md               box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1)
shadow-lg               box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1)
shadow-xl               box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1)
shadow-2xl              box-shadow: 0 25px 50px -12px rgb(0 0 0 / 0.25)
shadow-inner            box-shadow: inset 0 2px 4px 0 rgb(0 0 0 / 0.05)
shadow-none             box-shadow: 0 0 #0000
```

### Opacity
```
opacity-0               opacity: 0
opacity-25              opacity: 0.25
opacity-50              opacity: 0.5
opacity-75              opacity: 0.75
opacity-100             opacity: 1
```

## Transitions & Animations Cheat Sheet

### Transition Property
```
transition              transition-property: all
transition-colors       transition-property: colors
transition-opacity      transition-property: opacity
transition-shadow       transition-property: shadow
transition-transform    transition-property: transform
transition-none         transition-property: none
```

### Transition Duration
```
duration-75             transition-duration: 75ms
duration-100            transition-duration: 100ms
duration-150            transition-duration: 150ms
duration-200            transition-duration: 200ms
duration-300            transition-duration: 300ms
duration-500            transition-duration: 500ms
duration-700            transition-duration: 700ms
duration-1000           transition-duration: 1000ms
```

### Transition Timing
```
ease-linear             transition-timing-function: linear
ease-in                 transition-timing-function: cubic-bezier(0.4, 0, 1, 1)
ease-out                transition-timing-function: cubic-bezier(0, 0, 0.2, 1)
ease-in-out             transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1)
```

### Animations
```
animate-none            animation: none
animate-spin            animation: spin 1s linear infinite
animate-ping            animation: ping 1s cubic-bezier(0, 0, 0.2, 1) infinite
animate-pulse           animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite
animate-bounce          animation: bounce 1s infinite
```

## Responsive Design Cheat Sheet

### Breakpoints
```
Default                 Mobile - 0px and up
sm:                     Small screens - 640px and up
md:                     Medium screens - 768px and up
lg:                     Large screens - 1024px and up
xl:                     Extra large screens - 1280px and up
2xl:                    2X large screens - 1536px and up
```

### Example Usage
```
<div class="text-center md:text-left lg:text-right">
  Text aligns differently at different screen sizes
</div>

<div class="block sm:flex lg:grid lg:grid-cols-3">
  Layout changes from block to flex to grid as screen size increases
</div>
```

## Pseudo-Classes Cheat Sheet

### State Variants
```
hover:                  When user hovers with mouse
focus:                  When element has focus
active:                 When element is active
disabled:               When element is disabled
visited:                When link is visited
checked:                When checkbox/radio is checked
first:                  First element in a list
last:                   Last element in a list
odd:                    Odd elements in a list
even:                   Even elements in a list
```

### Example Usage
```
<button class="bg-blue-500 hover:bg-blue-700">
  Button changes color on hover
</button>

<input class="border focus:border-blue-500 focus:ring-2">
  Input gets blue border and ring when focused
</input>
```

## Print-Friendly Version

For a printable version of these cheat sheets, visit:
[https://tailwindcomponents.com/cheatsheet/](https://tailwindcomponents.com/cheatsheet/) 