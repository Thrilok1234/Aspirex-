# Aspirex-
New repo

1. using tailwind
2. docs: https://tailwindcss.com/docs/installation/using-vite

# main content to be added (arme)
1. aspirex intro, arme intro, workshop intro
2. nav bar should have home, events, workshops, contact us and a register button that takes to all register-able things in arme
3. in home, start with arme intro (desc and logo), then
4. our symposium - ASPIREX (desc, logo and a button to goto aspirex page)
5. news section, having stuff about upcoming workshops, events etc
6. then our contact us page, should have office bearers info

# arme decription
The Association of Robotics and Mechatronics Engineers (ARME), a student-driven force within the Society of Robotics and Mechatronics at AU-MIT, unites robotics and mechatronics engineering enthusiasts with a bold vision. Our mission is to ignite curiosity and steer young minds toward groundbreaking technologies and unconventional ideas. As a college association, we thrive on pushing boundaries, dreaming beyond the ordinary, and crafting a future where innovation knows no limits.

# aspirex desc
ASPIREX, forged by AU-MIT’s Robotics and Mechatronics Department students, crashes into action this April 12th with a surge of high-octane tech challenges and workshops. Hosted by ARME, this annual clash is where sweat, ingenuity, and a bit of chaos fuel the next big breakthrough.

# TIPS FOR MAKING WEBSITE MOBILE FRIENDLY USING TAILWIND

Making your website mobile-friendly using Tailwind CSS is a smart move—it’s a utility-first framework that makes responsive design straightforward and efficient. Here are some practical tips to get you started, tailored for a beginner-to-intermediate level:

1. **Leverage Tailwind’s Mobile-First Approach**
   - Tailwind uses a mobile-first philosophy, meaning styles are applied to smaller screens by default, and you add breakpoints (like `sm:`, `md:`, `lg:`) to adjust for larger screens.
   - Example: Instead of writing `text-lg` (large text for all screens), use `text-base sm:text-lg` to keep text smaller on mobile and larger on desktop.
   - Tip: Start designing for mobile, then scale up—think about how your ARME or ASPIREX content looks on a small screen first.

2. **Use Responsive Breakpoints**
   - Tailwind’s default breakpoints are: `sm` (640px), `md` (768px), `lg` (1024px), `xl` (1280px), and `2xl` (1536px).
   - Adjust layouts dynamically. For instance:
     ```html
     <div class="flex flex-col md:flex-row">
       <div class="w-full md:w-1/2">Content 1</div>
       <div class="w-full md:w-1/2">Content 2</div>
     </div>
     ```
     - On mobile (`flex-col`), it stacks vertically; on medium screens and up (`md:flex-row`), it switches to a row.

3. **Optimize Typography for Mobile**
   - Keep font sizes legible on small screens. Use relative units or Tailwind’s scale:
     ```html
     <h1 class="text-xl sm:text-2xl md:text-3xl">ASPIREX</h1>
     ```
   - Avoid tiny text—`text-sm` (0.875rem) is fine for minor details, but stick to `text-base` (1rem) or higher for body text on mobile.

4. **Handle Images Responsively**
   - Use `w-full` and `h-auto` to make images scale with their container:
     ```html
     <img src="robotics.jpg" class="w-full h-auto" alt="Robotics Event" />
     ```
   - Add `max-w-full` to prevent overflow on small screens.
   - For hero sections, consider `object-cover` with a fixed height:
     ```html
     <div class="w-full h-64">
       <img src="hero.jpg" class="w-full h-full object-cover" alt="ASPIREX Banner" />
     </div>
     ```

5. **Simplify Navigation for Mobile**
   - Create a hamburger menu for mobile using Tailwind and a bit of JavaScript:
     ```html
     <nav class="flex flex-col md:flex-row">
       <button class="md:hidden">☰</button>
       <div class="hidden md:flex flex-col md:flex-row">
         <a href="#" class="p-2">Home</a>
         <a href="#" class="p-2">About Us</a>
         <a href="#" class="p-2">ASPIREX</a>
       </div>
     </nav>
     ```
   - Use `md:hidden` to hide/show elements based on screen size. Toggle the menu with JS for mobile.

6. **Control Spacing and Padding**
   - Mobile screens need breathing room, but not too much. Use Tailwind’s spacing utilities:
     ```html
     <section class="p-4 sm:p-6 md:p-8">
       <p class="text-base">Welcome to ARME!</p>
     </section>
     ```
   - `p-4` (1rem) is great for mobile; scale up with `sm:p-6` or `md:p-8` for larger screens.

7. **Grid Layouts for Flexibility**
   - Use Tailwind’s grid system for responsive content blocks:
     ```html
     <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
       <div>Event 1</div>
       <div>Event 2</div>
       <div>Event 3</div>
     </div>
     ```
   - One column on mobile (`grid-cols-1`), two on small screens (`sm:grid-cols-2`), three on medium (`md:grid-cols-3`).

8. **Test with Tailwind’s Built-In Tools**
   - Add `debug-screens` to your Tailwind config to see breakpoint labels on-screen while testing:
     ```js
     module.exports = {
       plugins: [require('@tailwindcss/debug-screens')],
     }
     ```
   - Use your browser’s dev tools (toggle device toolbar) to simulate mobile views.

9. **Keep Performance in Mind**
   - Minimize heavy assets for mobile users. Compress images before uploading.
   - Avoid overloading with too many classes—Tailwind’s utility approach is lightweight, but keep your HTML clean.

Quick Example for ARME/ASPIREX
```html
<!DOCTYPE html>
<html>
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">
  <header class="bg-blue-600 text-white p-4">
    <h1 class="text-xl sm:text-2xl">ASPIREX - April 12th</h1>
  </header>
  <main class="p-4">
    <p class="text-base md:text-lg">Built by AU-MIT’s Robotics and Mechatronics Dept students, this yearly fest is where tech dreams get real.</p>
    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mt-4">
      <div class="bg-white p-4 rounded">Event Highlight 1</div>
      <div class="bg-white p-4 rounded">Event Highlight 2</div>
    </div>
  </main>
</body>
</html>
```
- Add the viewport meta tag (`<meta name="viewport" content="width=device-width, initial-scale=1.0">`) to ensure proper scaling on mobile.

### Final Tip
Start small—build one section (like your "About Us" or "ASPIREX" blurb) and test it on your phone. Adjust padding, text size, and layout until it feels snappy and readable. Tailwind’s flexibility lets you iterate fast, so play around and have fun making it your own! Let me know if you need help with a specific section.
