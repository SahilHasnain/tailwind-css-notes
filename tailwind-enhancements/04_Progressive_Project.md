# Progressive Project: Building a Landing Page with Tailwind CSS

This tutorial guides you through building a complete landing page using Tailwind CSS, applying concepts from simple to complex.

## Project Overview

We'll build a modern landing page for a fictional SaaS product called "TaskMaster" with these components:
- Navigation bar
- Hero section
- Feature cards
- Pricing section
- Testimonials
- FAQ accordion
- Contact form
- Footer

## Prerequisites

- Basic HTML/CSS knowledge
- Text editor
- Tailwind CSS via CDN (for simplicity)

## Step 1: Setting Up the Project

Create an `index.html` file with the Tailwind CDN:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TaskMaster - Simplify Your Workflow</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="font-sans text-gray-800 antialiased">
  <!-- Content will go here -->
</body>
</html>
```

## Step 2: Creating the Navigation Bar

Add this between the `<body>` tags:

```html
<!-- Navigation -->
<nav class="bg-white shadow-lg">
  <div class="max-w-6xl mx-auto px-4">
    <div class="flex justify-between items-center h-16">
      <!-- Logo -->
      <div class="flex items-center">
        <span class="text-blue-600 text-xl font-bold">TaskMaster</span>
      </div>
      
      <!-- Desktop Navigation -->
      <div class="hidden md:flex space-x-8">
        <a href="#features" class="text-gray-600 hover:text-blue-600 transition">Features</a>
        <a href="#pricing" class="text-gray-600 hover:text-blue-600 transition">Pricing</a>
        <a href="#testimonials" class="text-gray-600 hover:text-blue-600 transition">Testimonials</a>
        <a href="#faq" class="text-gray-600 hover:text-blue-600 transition">FAQ</a>
      </div>
      
      <!-- CTA Button -->
      <div class="hidden md:flex">
        <a href="#contact" class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700 transition">Get Started</a>
      </div>
      
      <!-- Mobile menu button -->
      <div class="md:hidden flex items-center">
        <button class="mobile-menu-button outline-none">
          <svg class="w-6 h-6 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
      </div>
    </div>
  </div>
  
  <!-- Mobile menu -->
  <div class="mobile-menu hidden md:hidden px-4 py-3 bg-gray-50">
    <a href="#features" class="block py-2 text-gray-600">Features</a>
    <a href="#pricing" class="block py-2 text-gray-600">Pricing</a>
    <a href="#testimonials" class="block py-2 text-gray-600">Testimonials</a>
    <a href="#faq" class="block py-2 text-gray-600">FAQ</a>
    <a href="#contact" class="block py-2 mt-2 bg-blue-600 text-white px-4 rounded">Get Started</a>
  </div>
</nav>
```

## Step 3: Building the Hero Section

Add after the navigation:

```html
<!-- Hero Section -->
<div class="bg-gradient-to-r from-blue-600 to-indigo-600 text-white">
  <div class="max-w-6xl mx-auto px-4 py-16 md:py-24 flex flex-col md:flex-row items-center">
    <!-- Left Column (Text) -->
    <div class="md:w-1/2 mb-10 md:mb-0">
      <h1 class="text-4xl md:text-5xl font-bold mb-6">Simplify Your Workflow</h1>
      <p class="text-xl mb-8">TaskMaster helps teams organize, track, and manage their work in a visual, productive, and rewarding way.</p>
      <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
        <a href="#contact" class="bg-white text-blue-600 font-bold py-3 px-6 rounded-lg hover:bg-gray-100 transition">Start Free Trial</a>
        <a href="#features" class="bg-transparent border-2 border-white text-white font-bold py-3 px-6 rounded-lg hover:bg-white hover:text-blue-600 transition">Learn More</a>
      </div>
    </div>
    
    <!-- Right Column (Image) -->
    <div class="md:w-1/2 md:pl-10">
      <img src="https://via.placeholder.com/600x400" alt="TaskMaster Dashboard" class="rounded-lg shadow-xl">
    </div>
  </div>
</div>
```

## Step 4: Feature Section

Add the feature cards:

```html
<!-- Features Section -->
<section id="features" class="bg-gray-50 py-16">
  <div class="max-w-6xl mx-auto px-4">
    <!-- Section Header -->
    <div class="text-center mb-16">
      <h2 class="text-3xl font-bold text-gray-800 mb-4">Powerful Features</h2>
      <p class="text-xl text-gray-600 max-w-2xl mx-auto">TaskMaster provides all the tools you need to manage projects effectively.</p>
    </div>
    
    <!-- Feature Cards -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <!-- Feature 1 -->
      <div class="bg-white p-6 rounded-lg shadow-md hover:shadow-xl transition">
        <div class="text-blue-600 mb-4">
          <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-3 7h3m-3 4h3m-6-4h.01M9 16h.01"></path>
          </svg>
        </div>
        <h3 class="text-xl font-bold mb-2">Task Management</h3>
        <p class="text-gray-600">Create, assign, and track tasks with ease. Set priorities and deadlines to keep everything on schedule.</p>
      </div>
      
      <!-- Feature 2 -->
      <div class="bg-white p-6 rounded-lg shadow-md hover:shadow-xl transition">
        <div class="text-blue-600 mb-4">
          <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"></path>
          </svg>
        </div>
        <h3 class="text-xl font-bold mb-2">Team Collaboration</h3>
        <p class="text-gray-600">Work together seamlessly. Share files, leave comments, and keep everyone in the loop.</p>
      </div>
      
      <!-- Feature 3 -->
      <div class="bg-white p-6 rounded-lg shadow-md hover:shadow-xl transition">
        <div class="text-blue-600 mb-4">
          <svg class="w-10 h-10" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"></path>
          </svg>
        </div>
        <h3 class="text-xl font-bold mb-2">Analytics & Reports</h3>
        <p class="text-gray-600">Get insights on productivity, track progress, and identify bottlenecks with powerful reports.</p>
      </div>
    </div>
  </div>
</section>
```

## Further Sections

The complete project includes these additional sections:
- Pricing tables with comparison features
- Testimonial carousel
- FAQ accordion with expandable answers
- Contact form with validation
- Responsive footer with sitemap and social links

To see the full code and final result, check out:
[TaskMaster Landing Page on CodePen](https://codepen.io/your-username/pen/taskmaster-landing)

## Key Tailwind Concepts Used

1. **Layout**
   - Flexbox (`flex`, `items-center`, `justify-between`)
   - Grid (`grid`, `grid-cols-3`, `gap-8`)
   - Responsive design (`md:flex-row`, `lg:grid-cols-3`)

2. **Styling**
   - Colors & gradients (`bg-blue-600`, `from-blue-600 to-indigo-600`)
   - Typography (`text-xl`, `font-bold`)
   - Spacing (`p-6`, `mb-4`, `space-x-4`)
   - Shadows (`shadow-md`, `shadow-xl`)

3. **Interactivity**
   - Hover effects (`hover:bg-blue-700`)
   - Transitions (`transition`)
   - Mobile menu toggle

4. **Organization**
   - Container constraints (`max-w-6xl mx-auto`)
   - Consistent spacing and alignment

## Learning Path Progression

This project demonstrates a logical progression through Tailwind concepts:
1. Basic utility classes (colors, spacing, typography)
2. Layout systems (flexbox and grid)
3. Responsive design (mobile-first approach)
4. Component patterns (cards, buttons, navigation)
5. Interactive elements (hover states, transitions)

By completing this project, you'll have gained practical experience with most of Tailwind's core features and be ready to build your own custom designs. 