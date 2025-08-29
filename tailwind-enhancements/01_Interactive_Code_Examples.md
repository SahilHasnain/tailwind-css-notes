# Interactive Tailwind CSS Examples

This resource provides live, interactive examples of Tailwind CSS concepts that you can experiment with directly in your browser.

## How to Use These Examples

1. Click on any CodePen link to open the live example
2. View the code and see the live result
3. Fork the CodePen to make your own modifications
4. Experiment with changing classes to see immediate results

## Basic Layout Examples

### Flexbox Layout

**[View on CodePen](https://codepen.io/your-username/pen/flexbox-example)**

This example demonstrates responsive Flexbox layout with Tailwind:
```html
<div class="flex flex-col md:flex-row gap-4 p-4">
  <div class="bg-blue-500 text-white p-4 rounded flex-1">Flex Item 1</div>
  <div class="bg-green-500 text-white p-4 rounded flex-1">Flex Item 2</div>
  <div class="bg-red-500 text-white p-4 rounded flex-1">Flex Item 3</div>
</div>
```

### Grid Layout

**[View on CodePen](https://codepen.io/your-username/pen/grid-example)**

This example shows a responsive grid layout that adapts from 1 column on mobile to 3 columns on desktop:
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 p-4">
  <div class="bg-purple-500 text-white p-4 rounded">Grid Item 1</div>
  <div class="bg-indigo-500 text-white p-4 rounded">Grid Item 2</div>
  <div class="bg-pink-500 text-white p-4 rounded">Grid Item 3</div>
  <div class="bg-yellow-500 text-white p-4 rounded">Grid Item 4</div>
  <div class="bg-blue-500 text-white p-4 rounded">Grid Item 5</div>
  <div class="bg-green-500 text-white p-4 rounded">Grid Item 6</div>
</div>
```

## Component Examples

### Interactive Card

**[View on CodePen](https://codepen.io/your-username/pen/card-example)**

A card with hover effects and transitions:
```html
<div class="max-w-sm mx-auto bg-white rounded-xl shadow-lg overflow-hidden transform hover:scale-105 transition duration-300">
  <img class="h-48 w-full object-cover" src="https://images.unsplash.com/photo-1541701494587-cb58502866ab?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1050&q=80" alt="Beach">
  <div class="p-6">
    <h2 class="font-bold text-xl mb-2 text-gray-800">Interactive Card</h2>
    <p class="text-gray-600">This card has a smooth hover effect with transition.</p>
    <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded transition duration-300">
      Learn More
    </button>
  </div>
</div>
```

### Responsive Navbar

**[View on CodePen](https://codepen.io/your-username/pen/navbar-example)**

A fully responsive navigation bar with mobile menu:
```html
<nav class="bg-blue-600 text-white">
  <!-- Desktop Navigation -->
  <div class="max-w-6xl mx-auto px-4">
    <div class="flex justify-between">
      <div class="flex space-x-4">
        <!-- Logo -->
        <div>
          <a href="#" class="flex items-center py-5 px-2 text-white">
            <span class="font-bold">TailwindNav</span>
          </a>
        </div>
        <!-- Primary Nav -->
        <div class="hidden md:flex items-center space-x-1">
          <a href="#" class="py-5 px-3 text-white hover:text-blue-200">Home</a>
          <a href="#" class="py-5 px-3 text-white hover:text-blue-200">Features</a>
          <a href="#" class="py-5 px-3 text-white hover:text-blue-200">Pricing</a>
        </div>
      </div>
      <!-- Sign In / Sign Up -->
      <div class="hidden md:flex items-center space-x-1">
        <a href="#" class="py-5 px-3">Login</a>
        <a href="#" class="py-2 px-3 bg-blue-700 hover:bg-blue-800 text-white rounded transition duration-300">Signup</a>
      </div>
      <!-- Mobile menu button -->
      <div class="md:hidden flex items-center">
        <button class="mobile-menu-button p-2 focus:outline-none">
          <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>
      </div>
    </div>
  </div>
  <!-- Mobile Menu -->
  <div class="mobile-menu hidden md:hidden p-4 bg-blue-700">
    <a href="#" class="block py-2 px-4 text-sm hover:bg-blue-800 rounded">Home</a>
    <a href="#" class="block py-2 px-4 text-sm hover:bg-blue-800 rounded">Features</a>
    <a href="#" class="block py-2 px-4 text-sm hover:bg-blue-800 rounded">Pricing</a>
    <div class="border-t border-blue-800 pt-2 mt-2">
      <a href="#" class="block py-2 px-4 text-sm hover:bg-blue-800 rounded">Login</a>
      <a href="#" class="block py-2 px-4 text-sm hover:bg-blue-800 rounded bg-blue-800 mt-1">Signup</a>
    </div>
  </div>
</nav>

<script>
  // Mobile menu functionality
  const btn = document.querySelector('.mobile-menu-button');
  const menu = document.querySelector('.mobile-menu');
  
  btn.addEventListener('click', () => {
    menu.classList.toggle('hidden');
  });
</script>
```

## Form Elements

### Styled Form

**[View on CodePen](https://codepen.io/your-username/pen/form-example)**

A form with styled inputs and validation states:
```html
<div class="max-w-md mx-auto bg-white p-8 rounded-lg shadow-md">
  <h2 class="text-2xl font-bold mb-6 text-gray-800">Contact Form</h2>
  <form>
    <div class="mb-4">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="name">
        Name
      </label>
      <input class="appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline focus:border-blue-500 transition" id="name" type="text" placeholder="Your name">
    </div>
    <div class="mb-4">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="email">
        Email
      </label>
      <input class="appearance-none border border-red-500 rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline focus:border-blue-500 transition" id="email" type="email" placeholder="Your email">
      <p class="text-red-500 text-xs italic mt-1">Please enter a valid email address.</p>
    </div>
    <div class="mb-6">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="message">
        Message
      </label>
      <textarea class="appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline focus:border-blue-500 transition" id="message" placeholder="Your message" rows="4"></textarea>
    </div>
    <div class="flex items-center justify-between">
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline transition duration-300" type="button">
        Send Message
      </button>
      <button class="bg-gray-200 hover:bg-gray-300 text-gray-700 font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline transition duration-300" type="button">
        Cancel
      </button>
    </div>
  </form>
</div>
```

## Animation Examples

### Loading Spinners

**[View on CodePen](https://codepen.io/your-username/pen/spinner-example)**

Different loading spinner styles with Tailwind:
```html
<div class="flex flex-wrap gap-8 justify-center p-8">
  <!-- Spinner 1: Simple Spin -->
  <div class="flex flex-col items-center">
    <div class="w-12 h-12 border-4 border-blue-200 border-t-blue-500 rounded-full animate-spin"></div>
    <p class="mt-2 text-sm text-gray-600">Basic Spinner</p>
  </div>
  
  <!-- Spinner 2: Ping Effect -->
  <div class="flex flex-col items-center">
    <div class="relative">
      <div class="w-12 h-12 bg-blue-500 rounded-full opacity-75 animate-ping absolute"></div>
      <div class="w-12 h-12 bg-blue-500 rounded-full relative"></div>
    </div>
    <p class="mt-2 text-sm text-gray-600">Ping Effect</p>
  </div>
  
  <!-- Spinner 3: Pulse -->
  <div class="flex flex-col items-center">
    <div class="w-12 h-12 bg-blue-500 rounded-full animate-pulse"></div>
    <p class="mt-2 text-sm text-gray-600">Pulse Effect</p>
  </div>
  
  <!-- Spinner 4: Bounce -->
  <div class="flex flex-col items-center">
    <div class="w-12 h-12 bg-blue-500 rounded-full animate-bounce"></div>
    <p class="mt-2 text-sm text-gray-600">Bounce Effect</p>
  </div>
</div>
```

### Button Transitions

**[View on CodePen](https://codepen.io/your-username/pen/button-transitions)**

Various button transitions and hover effects:
```html
<div class="p-8 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  <!-- Scale Button -->
  <div class="flex justify-center">
    <button class="bg-purple-500 hover:bg-purple-700 text-white font-bold py-2 px-6 rounded transform hover:scale-110 transition duration-300">
      Scale on Hover
    </button>
  </div>
  
  <!-- Translate Button -->
  <div class="flex justify-center">
    <button class="bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-6 rounded transform hover:-translate-y-1 transition duration-300">
      Move Up on Hover
    </button>
  </div>
  
  <!-- Rotate Button -->
  <div class="flex justify-center">
    <button class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-6 rounded transform hover:rotate-3 transition duration-300">
      Rotate on Hover
    </button>
  </div>
  
  <!-- Color Transition -->
  <div class="flex justify-center">
    <button class="bg-gradient-to-r from-purple-500 to-blue-500 hover:from-purple-600 hover:to-blue-600 text-white font-bold py-2 px-6 rounded transition duration-300">
      Gradient Transition
    </button>
  </div>
  
  <!-- Shadow Transition -->
  <div class="flex justify-center">
    <button class="bg-yellow-500 hover:bg-yellow-600 text-white font-bold py-2 px-6 rounded shadow-md hover:shadow-xl transition duration-300">
      Shadow Transition
    </button>
  </div>
  
  <!-- Width Transition -->
  <div class="flex justify-center">
    <button class="bg-pink-500 hover:bg-pink-600 text-white font-bold py-2 px-6 rounded hover:px-10 transition-all duration-300">
      Width Transition
    </button>
  </div>
</div>
```

## Create Your Own Examples

To create your own interactive examples:

1. Go to [CodePen](https://codepen.io) and create a new pen
2. Add the Tailwind CSS CDN to the pen:
   ```html
   <script src="https://cdn.tailwindcss.com"></script>
   ```
3. Experiment with different Tailwind classes
4. Share your example with others by saving and generating a link 