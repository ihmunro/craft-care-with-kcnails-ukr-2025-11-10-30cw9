# KCNails UKR Landing Page - Maintenance & Customization Guide

## Table of Contents

1. [Overview](#overview)
2. [Understanding the Page Structure](#understanding-the-page-structure)
3. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
4. [Fixing Broken Links](#fixing-broken-links)
5. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
6. [Common Tasks & Troubleshooting](#common-tasks--troubleshooting)
7. [Best Practices](#best-practices)

---

## Overview

This README provides comprehensive guidance for maintaining and customizing the KCNails UKR landing page. Whether you're updating content, fixing links, or adding new pages, this guide will walk you through each process step-by-step.

**Key Technologies Used:**
- **HTML5** - Page structure and content
- **Tailwind CSS** - Responsive styling via CDN
- **Font Awesome 6.4.0** - Icons throughout the page
- **Vanilla JavaScript** - Interactive elements (mobile menu, FAQ accordion)

---

## Understanding the Page Structure

The landing page is organized into distinct sections. Understanding this structure will help you navigate and modify content effectively.

### Main Page Sections

```
┌─────────────────────────────────────────┐
│  Header & Navigation (Sticky)           │
├─────────────────────────────────────────┤
│  Hero Section                           │
├─────────────────────────────────────────┤
│  Features Section (#features)           │
├─────────────────────────────────────────┤
│  Benefits Section (#benefits)           │
├─────────────────────────────────────────┤
│  Testimonials Section (#testimonials)   │
├─────────────────────────────────────────┤
│  About Us Section (#about)              │
├─────────────────────────────────────────┤
│  Call-to-Action Section                 │
├─────────────────────────────────────────┤
│  FAQ Section (#faq)                     │
├─────────────────────────────────────────┤
│  Footer                                 │
└─────────────────────────────────────────┘
```

### File Organization

```
project-folder/
├── index.html (main landing page)
├── privacy.html (privacy policy - needs to be created)
├── terms.html (terms of service - needs to be created)
├── blog.html (blog page - needs to be created)
└── README.md (this file)
```

---

## Updating Text and Tailwind CSS Classes

### What is Tailwind CSS?

Tailwind CSS is a utility-first CSS framework that uses class names to style elements. Instead of writing custom CSS, you add classes directly to HTML elements. For example:

```html
<!-- This creates a large, bold, purple text -->
<h1 class="text-5xl font-bold text-purple-600">
    My Heading
</h1>
```

The classes mean:
- `text-5xl` = very large text size
- `font-bold` = thick, heavy text
- `text-purple-600` = purple color

### Task 1: Updating Hero Section Heading

The hero section is the large banner at the top of the page. Here's how to update it:

**Location:** Find this code near line 120:

```html
<h1 class="text-5xl md:text-6xl lg:text-7xl font-bold text-gray-900 leading-tight tracking-tight">
    Craft & Care with <span class="bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent">KCNails UKR</span>
</h1>
```

**To change the text:**

1. Open `index.html` in your text editor
2. Find the `<h1>` tag with "Craft & Care with KCNails UKR"
3. Replace the text inside the `<h1>` tags, but keep the `<span>` tags intact:

```html
<!-- BEFORE -->
<h1 class="text-5xl md:text-6xl lg:text-7xl font-bold text-gray-900 leading-tight tracking-tight">
    Craft & Care with <span class="bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent">KCNails UKR</span>
</h1>

<!-- AFTER - Change only the text, not the classes -->
<h1 class="text-5xl md:text-6xl lg:text-7xl font-bold text-gray-900 leading-tight tracking-tight">
    Your New Title <span class="bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent">with Gradient</span>
</h1>
```

**What the classes mean:**
- `text-5xl md:text-6xl lg:text-7xl` = Different sizes for different screen sizes
  - `text-5xl` = mobile (small screens)
  - `md:text-6xl` = medium screens (tablets)
  - `lg:text-7xl` = large screens (desktops)
- `font-bold` = Makes text thick and heavy
- `text-gray-900` = Dark gray color
- `leading-tight` = Space between lines of text
- `tracking-tight` = Space between letters

### Task 2: Updating Section Headings

**Location:** Features section heading (around line 300):

```html
<h2 class="text-4xl md:text-5xl font-bold text-gray-900 tracking-tight">
    Why Choose KCNails UKR?
</h2>
```

**To update:**

```html
<!-- Simply replace the text -->
<h2 class="text-4xl md:text-5xl font-bold text-gray-900 tracking-tight">
    Why Our Customers Love Us
</h2>
```

**Repeat this process for:**
- Benefits Section (line ~450): "Experience the Difference"
- Testimonials Section (line ~650): "Loved by Our Customers"
- About Section (line ~1050): "Our Story & Mission"
- FAQ Section (line ~1350): "Frequently Asked Questions"

### Task 3: Updating Paragraph Text

**Location:** Hero section paragraph (around line 127):

```html
<p class="text-xl md:text-2xl text-gray-600 leading-relaxed">
    Find everything for stunning nails and support a country in need. Discover our premium collection of eco-conscious nail products designed for the modern, conscious consumer.
</p>
```

**To update:**

```html
<p class="text-xl md:text-2xl text-gray-600 leading-relaxed">
    Your new paragraph text goes here. Keep the classes the same.
</p>
```

**What these classes do:**
- `text-xl md:text-2xl` = Responsive text size
- `text-gray-600` = Medium gray color
- `leading-relaxed` = Comfortable space between lines

### Task 4: Changing Colors

Colors in Tailwind follow a pattern: `color-intensity`

**Common colors used in this page:**
- `purple-600` = Medium purple
- `pink-600` = Medium pink
- `gray-900` = Very dark gray (almost black)
- `gray-600` = Medium gray
- `green-500` = Bright green

**To change a button color from purple to blue:**

```html
<!-- BEFORE - Purple button -->
<a href="https://kcnailsukr.com/" class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-4 rounded-full">
    Shop Now
</a>

<!-- AFTER - Blue button -->
<a href="https://kcnailsukr.com/" class="bg-gradient-to-r from-blue-600 to-cyan-600 text-white px-8 py-4 rounded-full">
    Shop Now
</a>
```

**Available color options in Tailwind:**
- `red`, `orange`, `yellow`, `green`, `teal`, `blue`, `indigo`, `purple`, `pink`

**Intensity levels:**
- `50` (very light), `100`, `200`, `300`, `400`, `500` (medium), `600`, `700`, `800`, `900` (very dark)

### Task 5: Updating Feature Cards

**Location:** Features section (around line 315):

```html
<div class="card-hover bg-white rounded-2xl p-8 shadow-md hover:shadow-xl">
    <div class="inline-flex items-center justify-center w-14 h-14 bg-gradient-to-r from-purple-100 to-pink-100 rounded-full mb-6">
        <svg class="w-7 h-7 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" stroke-width="1.5">
            <!-- Icon SVG code -->
        </svg>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-3">Sustainable Packaging</h3>
    <p class="text-gray-600 leading-relaxed mb-4">
        Every product arrives in eco-friendly...
    </p>
```

**To update a feature card:**

```html
<div class="card-hover bg-white rounded-2xl p-8 shadow-md hover:shadow-xl">
    <div class="inline-flex items-center justify-center w-14 h-14 bg-gradient-to-r from-blue-100 to-cyan-100 rounded-full mb-6">
        <svg class="w-7 h-7 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" stroke-width="1.5">
            <!-- Icon SVG code - keep as is -->
        </svg>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-3">Your New Feature Title</h3>
    <p class="text-gray-600 leading-relaxed mb-4">
        Your new feature description goes here.
    </p>
```

**Key classes for cards:**
- `bg-white` = White background
- `rounded-2xl` = Rounded corners
- `p-8` = Padding (space inside the card)
- `shadow-md` = Subtle shadow
- `hover:shadow-xl` = Larger shadow on hover

### Task 6: Updating Testimonials

**Location:** Testimonials section (around line 750):

```html
<div class="card-hover bg-white rounded-2xl p-8 shadow-md hover:shadow-xl">
    <div class="flex items-center mb-4">
        <div class="flex space-x-1">
            <!-- Star ratings -->
        </div>
    </div>
    <p class="text-gray-600 mb-6 leading-relaxed">
        "The quality of these nail products is absolutely exceptional!..."
    </p>
    <div class="border-t pt-4">
        <p class="font-bold text-gray-900">Sarah Mitchell</p>
        <p class="text-sm text-gray-600">Beauty Enthusiast, London</p>
    </div>
</div>
```

**To update a testimonial:**

```html
<div class="card-hover bg-white rounded-2xl p-8 shadow-md hover:shadow-xl">
    <div class="flex items-center mb-4">
        <div class="flex space-x-1">
            <!-- Keep star ratings as is -->
        </div>
    </div>
    <p class="text-gray-600 mb-6 leading-relaxed">
        "Your new testimonial text goes here. Keep it between quotation marks."
    </p>
    <div class="border-t pt-4">
        <p class="font-bold text-gray-900">Customer Name</p>
        <p class="text-sm text-gray-600">Job Title, City</p>
    </div>
</div>
```

### Task 7: Changing Button Styles

**Location:** Multiple locations throughout the page

**Default button (filled):**
```html
<a href="https://kcnailsukr.com/" class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-4 rounded-full button-base">
    Shop Now
</a>
```

**Outline button (border only):**
```html
<a href="#benefits" class="border-2 border-purple-600 text-purple-600 px-8 py-4 rounded-full button-base hover:bg-purple-50">
    Learn More
</a>
```

**Class breakdown:**
- `bg-gradient-to-r from-purple-600 to-pink-600` = Gradient background
- `text-white` = White text
- `px-8` = Horizontal padding (left and right)
- `py-4` = Vertical padding (top and bottom)
- `rounded-full` = Completely rounded corners
- `button-base` = Custom hover effect (defined in `<style>` tag)

### Task 8: Adjusting Spacing

Spacing is controlled by padding (`p-`) and margin (`m-`) classes:

```html
<!-- Add more space inside -->
<div class="p-8">Content</div>  <!-- p-8 = more padding -->
<div class="p-4">Content</div>  <!-- p-4 = less padding -->

<!-- Add more space outside -->
<div class="mb-6">Content</div>  <!-- mb-6 = margin bottom -->
<div class="mt-4">Content</div>  <!-- mt-4 = margin top -->
```

**Common spacing values:**
- `2`, `4`, `6`, `8`, `12`, `16`, `24`, `32`

---

## Fixing Broken Links

### Understanding Links in HTML

A link in HTML looks like this:

```html
<a href="https://example.com">Click Me</a>
```

Breaking it down:
- `<a>` = anchor tag (creates a link)
- `href="..."` = the destination of the link
- `Click Me` = the text users see and click on

### Task 1: Update Navigation Menu Links

**Location:** Header navigation (around line 60):

```html
<div class="hidden md:flex items-center space-x-8">
    <a href="#features" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Features</a>
    <a href="#benefits" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Benefits</a>
    <a href="#testimonials" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Testimonials</a>
    <a href="#about" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">About</a>
    <a href="#faq" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">FAQ</a>
    <a href="https://kcnailsukr.com/" class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-2 rounded-full button-base font-semibold">
        Shop Now
    </a>
</div>
```

**These links use two types:**

1. **Internal links** (start with `#`):
   - `href="#features"` = jumps to the section with `id="features"`
   - `href="#benefits"` = jumps to the section with `id="benefits"`
   - These work because the page has matching sections

2. **External links** (start with `https://`):
   - `href="https://kcnailsukr.com/"` = goes to external website
   - Opens in the same tab by default

**To update the Shop Now link:**

```html
<!-- BEFORE -->
<a href="https://kcnailsukr.com/" class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-2 rounded-full button-base font-semibold">
    Shop Now
</a>

<!-- AFTER - Update only the href -->
<a href="https://your-new-shop-url.com/" class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-2 rounded-full button-base font-semibold">
    Shop Now
</a>
```

### Task 2: Update Mobile Menu Links

**Location:** Mobile menu (around line 80):

```html
<div class="mobile-menu hidden md:hidden pb-4">
    <a href="#features" class="block px-3 py-2 rounded-md text-gray-700 hover:bg-purple-50 transition-smooth">Features</a>
    <a href="#benefits" class="block px-3 py-2 rounded-md text-gray-700 hover:bg-purple-50 transition-smooth">Benefits</a>
    <a href="#testimonials" class="block px-3 py-2 rounded-md text-gray-700 hover:bg-purple-50 transition-smooth">Testimonials</a>
    <a href="#about" class="block px-3 py-2 rounded-md text-gray-700 hover:bg-purple-50 transition-smooth">About</a>
    <a href="#faq" class="block px-3 py-2 rounded-md text-gray-700 hover:bg-purple-50 transition-smooth">FAQ</a>
    <a href="https://kcnailsukr.com/" class="block mt-4 bg-gradient-to-r from-purple-600 to-pink-600 text-white px-6 py-3 rounded-full text-center button-base font-semibold">
        Shop Now
    </a>
</div>
```

**Important:** The mobile menu links should match the desktop menu links. If you update one, update both.

**To update:**

```html
<!-- Update the Shop Now link in mobile menu -->
<a href="https://your-new-shop-url.com/" class="block mt-4 bg-gradient-to-r from-purple-600 to-pink-600 text-white px-6 py-3 rounded-full text-center button-base font-semibold">
    Shop Now
</a>
```

### Task 3: Update "Explore Collection" Button

**Location:** Hero section (around line 135):

```html
<a href="https://kcnailsukr.com/" class="inline-flex items-center justify-center bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-4 rounded-full text-lg font-bold button-base shadow-lg hover:shadow-xl">
    Explore Collection
    <svg class="w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"></path>
    </svg>
</a>
```

**To update:**

```html
<a href="https://your-new-shop-url.com/" class="inline-flex items-center justify-center bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-4 rounded-full text-lg font-bold button-base shadow-lg hover:shadow-xl">
    Explore Collection
    <svg class="w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"></path>
    </svg>
</a>
```

### Task 4: Update CTA Section Buttons

**Location:** Call-to-action section (around line 1300):

```html
<a href="https://kcnailsukr.com/" class="inline-flex items-center justify-center bg-white text-purple-600 px-8 py-4 rounded-full text-lg font-bold button-base shadow-lg hover:shadow-xl">
    Shop the Collection
    <svg class="w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"></path>
    </svg>
</a>
```

**To update:**

```html
<a href="https://your-new-shop-url.com/" class="inline-flex items-center justify-center bg-white text-purple-600 px-8 py-4 rounded-full text-lg font-bold button-base shadow-lg hover:shadow-xl">
    Shop the Collection
    <svg class="w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"></path>
    </svg>
</a>
```

### Task 5: Update Footer Links

**Location:** Footer (around line 1400):

```html
<ul class="space-y-3">
    <li><a href="https://kcnailsukr.com/" class="text-gray-400 hover:text-purple-400 transition-smooth">Shop</a></li>
    <li><a href="#about" class="text-gray-400 hover:text-purple-400 transition-smooth">About Us</a></li>
    <li><a href="#features" class="text-gray-400 hover:text-purple-400 transition-smooth">Features</a></li>
    <li><a href="#faq" class="text-gray-400 hover:text-purple-400 transition-smooth">FAQ</a></li>
</ul>
```

**To update the Shop link:**

```html
<ul class="space-y-3">
    <li><a href="https://your-new-shop-url.com/" class="text-gray-400 hover:text-purple-400 transition-smooth">Shop</a></li>
    <li><a href="#about" class="text-gray-400 hover:text-purple-400 transition-smooth">About Us</a></li>
    <li><a href="#features" class="text-gray-400 hover:text-purple-400 transition-smooth">Features</a></li>
    <li><a href="#faq" class="text-gray-400 hover:text-purple-400 transition-smooth">FAQ</a></li>
</ul>
```

### Task 6: Update Contact Email Link

**Location:** Footer contact section (around line 1430):

```html
<a href="mailto:iainhmunro@gmail.com" class="text-gray-400 hover:text-purple-400 transition-smooth break-all">
    iainhmunro@gmail.com
</a>
```

**To update:**

```html
<a href="mailto:your-email@example.com" class="text-gray-400 hover:text-purple-400 transition-smooth break-all">
    your-email@example.com
</a>
```

**Note:** When updating email links, change both the `href="mailto:..."` AND the visible email text to match.

### Task 7: Update Social Media Links

**Location:** Footer social links (around line 1375):

```html
<div class="flex space-x-4 pt-4">
    <a href="#" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-purple-600 flex items-center justify-center transition-smooth">
        <i class="fab fa-facebook-f text-white"></i>
    </a>
    <a href="#" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-purple-600 flex items-center justify-center transition-smooth">
        <i class="fab fa-instagram text-white"></i>
    </a>
    <a href="#" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-purple-600 flex items-center justify-center transition-smooth">
        <i class="fab fa-twitter text-white"></i>
    </a>
    <a href="#" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-purple-600 flex items-center justify-center transition-smooth">
        <i class="fab fa-linkedin-in text-white"></i>
    </a>
</div>
```

**To update with real social media links:**

```html
<div class="flex space-x-4 pt-4">
    <a href="https://www.facebook.com/kcnailsukr" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-purple-600 flex items-center justify-center transition-smooth">
        <i class="fab fa-facebook-f text-white"></i>
    </a>
    <a href="https://www.instagram.com/kcnailsukr" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-purple-600 flex items-center justify-center transition-smooth">
        <i class="fab fa-instagram text-white"></i>
    </a>
    <a href="https://www.twitter.com/kcnailsukr" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-purple-600 flex items-center justify-center transition-smooth">
        <i class="fab fa-twitter text-white"></i>
    </a>
    <a href="https://www.linkedin.com/company/kcnailsukr" class="w-10 h-10 rounded-full bg-gray-800 hover:bg-purple-600 flex items-center justify-center transition-smooth">
        <i class="fab fa-linkedin-in text-white"></i>
    </a>
</div>
```

### Task 8: Update "Contact Us" Link

**Location:** Footer support section (around line 1415):

```html
<li><a href="mailto:iainhmunro@gmail.com" class="text-gray-400 hover:text-purple-400 transition-smooth">Contact Us</a></li>
```

**To update:**

```html
<li><a href="mailto:your-email@example.com" class="text-gray-400 hover:text-purple-400 transition-smooth">Contact Us</a></li>
```

### Troubleshooting Broken Links

**Problem:** Link doesn't work or goes to wrong page

**Solution checklist:**

1. **Check the URL is correct:**
   ```html
   <!-- ✓ CORRECT - Has https:// -->
   <a href="https://example.com">Link</a>
   
   <!-- ✗ WRONG - Missing https:// -->
   <a href="example.com">Link</a>
   ```

2. **Check internal links have matching IDs:**
   ```html
   <!-- Link points to #features -->
   <a href="#features">Go to Features</a>
   
   <!-- Section must have matching id -->
   <section id="features">
       Content here
   </section>
   ```

3. **Check for typos:**
   ```html
   <!-- ✗ WRONG - typo in URL -->
   <a href="https://kcnailsukr.co">Link</a>
   
   <!-- ✓ CORRECT -->
   <a href="https://kcnailsukr.com/">Link</a>
   ```

4. **Check email links use mailto:**
   ```html
   <!-- ✓ CORRECT -->
   <a href="mailto:email@example.com">Email</a>
   
   <!-- ✗ WRONG - Missing mailto: -->
   <a href="email@example.com">Email</a>
   ```

---

## Linking Privacy and Terms Pages

### Understanding the Need for Policy Pages

Privacy and Terms pages are legal documents that explain:
- **Privacy Policy:** How you collect and use customer data
- **Terms of Service:** Rules customers must follow when using your site

These pages are linked in the footer and referenced in various places on the site.

### Step 1: Create the Privacy Policy Page

**File name:** `privacy.html`

**Location:** Save in the same folder as `index.html`

**Template to use:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Privacy Policy - KCNails UKR">
    <title>Privacy Policy - KCNails UKR</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body class="bg-white text-gray-900 font-sans">
    <!-- Header (Same as index.html) -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex-shrink-0">
                    <a href="index.html" class="text-2xl font-bold bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent">
                        KCNails UKR
                    </a>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="index.html#features" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Features</a>
                    <a href="index.html#benefits" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Benefits</a>
                    <a href="index.html#testimonials" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Testimonials</a>
                    <a href="index.html#about" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">About</a>
                    <a href="index.html#faq" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">FAQ</a>
                    <a href="https://kcnailsukr.com/" class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-2 rounded-full font-semibold">
                        Shop Now
                    </a>
                </div>
            </div>
        </nav>
    </header>

    <!-- Main Content -->
    <section class="py-24 md:py-32 bg-gray-50">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-5xl font-bold text-gray-900 mb-8">Privacy Policy</h1>
            
            <div class="bg-white rounded-2xl p-8 shadow-md space-y-8">
                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">1. Introduction</h2>
                    <p class="text-gray-700 leading-relaxed">
                        At KCNails UKR, we are committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you visit our website.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">2. Information We Collect</h2>
                    <p class="text-gray-700 leading-relaxed mb-4">
                        We may collect information about you in a variety of ways. The information we may collect on the site includes:
                    </p>
                    <ul class="list-disc list-inside text-gray-700 space-y-2">
                        <li>Personal Data (name, email address, phone number)</li>
                        <li>Payment Information (processed securely)</li>
                        <li>Usage Data (pages visited, time spent, links clicked)</li>
                        <li>Device Information (IP address, browser type, operating system)</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">3. How We Use Your Information</h2>
                    <p class="text-gray-700 leading-relaxed mb-4">
                        Having accurate information about you permits us to provide you with a smooth, efficient, and customized experience. Specifically, we may use information collected about you via the site to:
                    </p>
                    <ul class="list-disc list-inside text-gray-700 space-y-2">
                        <li>Process your transactions and send related information</li>
                        <li>Email you regarding your order status</li>
                        <li>Fulfill and manage purchases, orders, payments, and other transactions related to our site</li>
                        <li>Generate a personal profile about you</li>
                        <li>Increase the efficiency and operation of our site</li>
                        <li>Monitor and analyze usage and trends to improve your experience with our site</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">4. Disclosure of Your Information</h2>
                    <p class="text-gray-700 leading-relaxed">
                        We may share information we have collected about you in certain situations:
                    </p>
                    <ul class="list-disc list-inside text-gray-700 space-y-2 mt-4">
                        <li><strong>By Law or to Protect Rights:</strong> If we believe the release of information is necessary</li>
                        <li><strong>Third-Party Service Providers:</strong> We may share your information with parties who assist us in operating our website and conducting our business</li>
                        <li><strong>Affiliate Marketing:</strong> We do not sell, trade, or otherwise transfer your personally identifiable information</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">5. Security of Your Information</h2>
                    <p class="text-gray-700 leading-relaxed">
                        We use administrative, technical, and physical security measures to protect your personal information. However, perfect security does not exist on the Internet.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">6. Contact Us</h2>
                    <p class="text-gray-700 leading-relaxed">
                        If you have questions or comments about this Privacy Policy, please contact us at:
                    </p>
                    <p class="text-gray-700 leading-relaxed mt-4">
                        Email: <a href="mailto:iainhmunro@gmail.com" class="text-purple-600 hover:text-purple-700">iainhmunro@gmail.com</a>
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer (Same as index.html) -->
    <footer class="bg-gray-900 text-gray-300 py-16">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="border-t border-gray-800 pt-8">
                <div class="flex flex-col md:flex-row justify-between items-center space-y-4 md:space-y-0">
                    <p class="text-gray-400 text-center md:text-left">
                        &copy; 2025 KCNails UKR. All rights reserved.
                    </p>
                    <div class="flex space-x-6">
                        <a href="privacy.html" class="text-gray-400 hover:text-purple-400 transition-smooth text-sm">Privacy</a>
                        <a href="terms.html" class="text-gray-400 hover:text-purple-400 transition-smooth text-sm">Terms</a>
                        <a href="blog.html" class="text-gray-400 hover:text-purple-400 transition-smooth text-sm">Blog</a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</body>
</html>
```

### Step 2: Create the Terms of Service Page

**File name:** `terms.html`

**Location:** Save in the same folder as `index.html`

**Template to use:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Terms of Service - KCNails UKR">
    <title>Terms of Service - KCNails UKR</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body class="bg-white text-gray-900 font-sans">
    <!-- Header (Same as index.html) -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex-shrink-0">
                    <a href="index.html" class="text-2xl font-bold bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent">
                        KCNails UKR
                    </a>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="index.html#features" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Features</a>
                    <a href="index.html#benefits" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Benefits</a>
                    <a href="index.html#testimonials" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Testimonials</a>
                    <a href="index.html#about" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">About</a>
                    <a href="index.html#faq" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">FAQ</a>
                    <a href="https://kcnailsukr.com/" class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-2 rounded-full font-semibold">
                        Shop Now
                    </a>
                </div>
            </div>
        </nav>
    </header>

    <!-- Main Content -->
    <section class="py-24 md:py-32 bg-gray-50">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <h1 class="text-5xl font-bold text-gray-900 mb-8">Terms of Service</h1>
            
            <div class="bg-white rounded-2xl p-8 shadow-md space-y-8">
                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">1. Agreement to Terms</h2>
                    <p class="text-gray-700 leading-relaxed">
                        By accessing and using the KCNails UKR website, you accept and agree to be bound by the terms and provision of this agreement. If you do not agree to abide by the above, please do not use this service.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">2. Use License</h2>
                    <p class="text-gray-700 leading-relaxed mb-4">
                        Permission is granted to temporarily download one copy of the materials (information or software) on KCNails UKR's website for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                    </p>
                    <ul class="list-disc list-inside text-gray-700 space-y-2">
                        <li>Modifying or copying the materials</li>
                        <li>Using the materials for any commercial purpose or for any public display</li>
                        <li>Attempting to decompile or reverse engineer any software contained on the website</li>
                        <li>Removing any copyright or other proprietary notations from the materials</li>
                        <li>Transferring the materials to another person or "mirroring" the materials on any other server</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">3. Disclaimer</h2>
                    <p class="text-gray-700 leading-relaxed">
                        The materials on KCNails UKR's website are provided on an 'as is' basis. KCNails UKR makes no warranties, expressed or implied, and hereby disclaims and negates all other warranties including, without limitation, implied warranties or conditions of merchantability, fitness for a particular purpose, or non-infringement of intellectual property or other violation of rights.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">4. Limitations</h2>
                    <p class="text-gray-700 leading-relaxed">
                        In no event shall KCNails UKR or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on the KCNails UKR website.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">5. Accuracy of Materials</h2>
                    <p class="text-gray-700 leading-relaxed">
                        The materials appearing on the KCNails UKR website could include technical, typographical, or photographic errors. KCNails UKR does not warrant that any of the materials on our website are accurate, complete, or current. KCNails UKR may make changes to the materials contained on its website at any time without notice.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">6. Links</h2>
                    <p class="text-gray-700 leading-relaxed">
                        KCNails UKR has not reviewed all of the sites linked to its website and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by KCNails UKR of the site. Use of any such linked website is at the user's own risk.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">7. Modifications</h2>
                    <p class="text-gray-700 leading-relaxed">
                        KCNails UKR may revise these terms of service for its website at any time without notice. By using this website, you are agreeing to be bound by the then current version of these terms of service.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">8. Governing Law</h2>
                    <p class="text-gray-700 leading-relaxed">
                        These terms and conditions are governed by and construed in accordance with the laws of the United Kingdom, and you irrevocably submit to the exclusive jurisdiction of the courts in that location.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">9. Contact Us</h2>
                    <p class="text-gray-700 leading-relaxed">
                        If you have any questions about these Terms of Service, please contact us at:
                    </p>
                    <p class="text-gray-700 leading-relaxed mt-4">
                        Email: <a href="mailto:iainhmunro@gmail.com" class="text-purple-600 hover:text-purple-700">iainhmunro@gmail.com</a>
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer (Same as index.html) -->
    <footer class="bg-gray-900 text-gray-300 py-16">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="border-t border-gray-800 pt-8">
                <div class="flex flex-col md:flex-row justify-between items-center space-y-4 md:space-y-0">
                    <p class="text-gray-400 text-center md:text-left">
                        &copy; 2025 KCNails UKR. All rights reserved.
                    </p>
                    <div class="flex space-x-6">
                        <a href="privacy.html" class="text-gray-400 hover:text-purple-400 transition-smooth text-sm">Privacy</a>
                        <a href="terms.html" class="text-gray-400 hover:text-purple-400 transition-smooth text-sm">Terms</a>
                        <a href="blog.html" class="text-gray-400 hover:text-purple-400 transition-smooth text-sm">Blog</a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</body>
</html>
```

### Step 3: Update Footer Links in index.html

The footer in `index.html` already has links to privacy and terms pages. Verify they are correct:

**Location:** Footer (around line 1415):

```html
<ul class="space-y-3">
    <li><a href="mailto:iainhmunro@gmail.com" class="text-gray-400 hover:text-purple-400 transition-smooth">Contact Us</a></li>
    <li><a href="privacy.html" class="text-gray-400 hover:text-purple-400 transition-smooth">Privacy Policy</a></li>
    <li><a href="terms.html" class="text-gray-400 hover:text-purple-400 transition-smooth">Terms of Service</a></li>
    <li><a href="blog.html" class="text-gray-400 hover:text-purple-400 transition-smooth">Blog</a></li>
</ul>
```

**And at the bottom:**

```html
<div class="flex space-x-6">
    <a href="privacy.html" class="text-gray-400 hover:text-purple-400 transition-smooth text-sm">Privacy</a>
    <a href="terms.html" class="text-gray-400 hover:text-purple-400 transition-smooth text-sm">Terms</a>
    <a href="blog.html" class="text-gray-400 hover:text-purple-400 transition-smooth text-sm">Blog</a>
</div>
```

These links are already correct! They point to `privacy.html` and `terms.html` which you just created.

### Step 4: Verify Links Work

**To test the links:**

1. Open `index.html` in your web browser
2. Scroll to the footer
3. Click on "Privacy Policy" - should open `privacy.html`
4. Click on "Terms of Service" - should open `terms.html`
5. On those pages, click the logo to return to `index.html`

### Step 5: Add Links in Header (Optional)

If you want to add Privacy and Terms links to the navigation menu:

**Location:** Desktop menu header (around line 60):

```html
<!-- BEFORE - No policy links -->
<div class="hidden md:flex items-center space-x-8">
    <a href="#features" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Features</a>
    <a href="#benefits" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Benefits</a>
    <a href="#testimonials" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Testimonials</a>
    <a href="#about" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">About</a>
    <a href="#faq" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">FAQ</a>
    <a href="https://kcnailsukr.com/" class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-2 rounded-full button-base font-semibold">
        Shop Now
    </a>
</div>

<!-- AFTER - Add policy links -->
<div class="hidden md:flex items-center space-x-8">
    <a href="#features" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Features</a>
    <a href="#benefits" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Benefits</a>
    <a href="#testimonials" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">Testimonials</a>
    <a href="#about" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">About</a>
    <a href="#faq" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium">FAQ</a>
    <a href="privacy.html" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium text-sm">Privacy</a>
    <a href="terms.html" class="text-gray-700 hover:text-purple-600 transition-smooth font-medium text-sm">Terms</a>
    <a href="https://kcnailsukr.com/" class="bg-gradient-to-r from-purple-600 to-pink-600 text-white px-8 py-2 rounded-full button-base font-semibold">
        Shop Now
    </a>
</div>
```

---

## Common Tasks & Troubleshooting

### Task 1: Change the Site's Main Color Scheme

The site uses purple and pink as primary colors. To change to blue and cyan:

**Step 1:** Find all instances of `purple-600` and replace with `blue-600`

**Step 2:** Find all instances of `pink-600` and replace with `cyan-600`

**Example:**

```html
<!-- BEFORE -->
<div class="bg-gradient-to-r from-purple-600 to-pink-600">
    Content
</div>

<!-- AFTER -->
<div class="bg-gradient-to-r from-blue-600 to-cyan-600">
    Content
</div>
```

**Where to find these:**
- Header buttons
- Hero section heading
- Feature card icons
- Buttons throughout the page
- Footer social icons

### Task 2: Add a New Feature Card

**Location:** Features section (around line 315)

**Template:**

```html
<!-- Copy an existing feature card and modify -->
<div class="card-hover bg-white rounded-2xl p-8 shadow-md hover:shadow-xl">
    <div class="inline-flex items-center justify-center w-14 h-14 bg-gradient-to-r from-purple-100 to-pink-100 rounded-full mb-6">
        <svg class="w-7 h-7 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24" stroke-width="1.5">
            <!-- Icon SVG - find on heroicons.com -->
        </svg>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-3">Your Feature Title</h3>
    <p class="text-gray-600 leading-relaxed mb-4">
        Your feature description goes here.
    </p>
    <ul class="space-y-2">
        <li class="flex items-center text-gray-700">
            <svg class="w-5 h-5 text-green-500 mr-2" fill="currentColor" viewBox="0 0 20 20">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
            </svg>
            Benefit point 1
        </li>
        <li class="flex items-center text-gray-700">
            <svg class="w-5 h-5 text-green-500 mr-2" fill="currentColor" viewBox="0 0 20 20">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
            </svg>
            Benefit point 2
        </li>
        <li class="flex items-center text-gray-700">
            <svg class="w-5 h-5 text-green-500 mr-2" fill="currentColor" viewBox="0 0 20 20">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
            </svg>
            Benefit point 3
        </li>
    </ul>
</div>
```

**Where to insert:** Add before the closing `</div>` of the features grid (around line 395)

### Task 3: Update the Hero Image

The hero section references an image placeholder. To add a real image:

**Location:** Hero section right side (around line 170)

```html
<!-- BEFORE - Placeholder -->
<div class="relative hidden lg:block">
    <div class="absolute inset-0 bg-gradient-to-r from-purple-400 to-pink-400 rounded-3xl transform rotate-6 opacity-20"></div>
    <div class="relative bg-gradient-to-br from-purple-100 to-pink-100 rounded-3xl p-8 shadow-2xl">
        <div class="aspect-square bg-gradient-to-br from-purple-300 via-pink-300 to-purple-300 rounded-2xl flex items-center justify-center">
            <svg class="w-32 h-32 text-white opacity-80" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"></path>
            </svg>
        </div>
    </div>
</div>

<!-- AFTER - With real image -->
<div class="relative hidden lg:block">
    <div class="absolute inset-0 bg-gradient-to-r from-purple-400 to-pink-400 rounded-3xl transform rotate-6 opacity-20"></div>
    <img src="path/to/your/image.jpg" alt="KCNails UKR products" class="relative rounded-3xl shadow-2xl w-full object-cover aspect-square">
</div>
```

### Task 4: Change Font Sizes

Tailwind text sizes: `text-sm`, `text-base`, `text-lg`, `text-xl`, `text-2xl`, `text-3xl`, `text-4xl`, `text-5xl`, `text-6xl`, `text-7xl`

**Example - Make a heading smaller:**

```html
<!-- BEFORE - Large heading -->
<h1 class="text-7xl font-bold">
    My Heading
</h1>

<!-- AFTER - Medium heading -->
<h1 class="text-4xl font-bold">
    My Heading
</h1>
```

### Task 5: Add or Remove Spacing

**Padding (inside):**
```html
<div class="p-4">Small padding</div>
<div class="p-8">Medium padding</div>
<div class="p-12">Large padding</div>
```

**Margin (outside):**
```html
<div class="mb-4">Small bottom margin</div>
<div class="mt-8">Medium top margin</div>
<div class="mx-6">Horizontal margins</div>
```

### Troubleshooting: Links Not Working

**Problem:** Link doesn't navigate anywhere

**Checklist:**

1. **Check file names match exactly:**
   ```
   ✓ CORRECT: privacy.html
   ✗ WRONG: Privacy.html (capital P)
   ✗ WRONG: privacy-policy.html (different name)
   ```

2. **Check file is in the same folder:**
   ```
   project-folder/
   ├── index.html
   ├── privacy.html  ← Must be here
   ├── terms.html    ← Must be here
   ```

3. **Check internal links have matching IDs:**
   ```html
   <!-- Link -->
   <a href="#features">Go to Features</a>
   
   <!-- Must have matching section -->
   <section id="features">
       Content
   </section>
   ```

### Troubleshooting: Styling Looks Wrong

**Problem:** Colors, sizes, or spacing look incorrect

**Solution:**

1. **Clear browser cache:**
   - Windows: Press `Ctrl + Shift + Delete`
   - Mac: Press `Cmd + Shift + Delete`

2. **Hard refresh the page:**
   - Windows: Press `Ctrl + Shift + R`
   - Mac: Press `Cmd + Shift + R`

3. **Check for typos in class names:**
   ```html
   ✓ CORRECT: text-purple-600
   ✗ WRONG: text-purpl-600 (typo)
   ✗ WRONG: text-purple600 (missing hyphen)
   ```

### Troubleshooting: Mobile Menu Not Working

**Problem:** Mobile menu doesn't open on small screens

**Solution:**

1. **Check JavaScript is enabled** (required for mobile menu)
2. **Check the mobile menu button exists:**
   ```html
   <button class="mobile-menu-button p-2 rounded-md text-gray-700 hover:text-purple-600 focus:outline-none">
       <i class="fas fa-bars text-xl"></i>
   </button>
   ```

3. **Check the mobile menu div exists:**
   ```html
   <div class="mobile-menu hidden md:hidden pb-4">
       <!-- Mobile menu links -->
   </div>
   ```

### Troubleshooting: FAQ Accordion Not Opening

**Problem:** FAQ questions don't expand when clicked

**Solution:**

1. **Check JavaScript is enabled**
2. **Check FAQ structure is correct:**
   ```html
   <div class="faq-item">
       <button class="faq-question">
           <span>Question?</span>
           <svg class="faq-icon"><!-- Icon --></svg>
       </button>
       <div class="faq-answer hidden">
           <p>Answer text</p>
       </div>
   </div>
   ```

---

## Best Practices

### 1. Always Backup Before Making Changes

Before editing `index.html`, create a backup:

```
index.html → index.html.backup
```

This way, if something goes wrong, you can restore the original.

### 2. Test Changes on Multiple Devices

After making changes, test on:
- **Desktop** (large screen)
- **Tablet** (medium screen)
- **Mobile** (small screen)

This ensures responsive design still works properly.

### 3. Use Descriptive Link Text

**Good:**
```html
<a href="privacy.html">Read our Privacy Policy</a>
```

**Bad:**
```html
<a href="privacy.html">Click here</a>
```

### 4. Keep Consistent Formatting

When editing HTML, maintain consistent indentation:

```html
<!-- GOOD - Consistent indentation -->
<div class="container">
    <h1>Title</h1>
    <p>Text</p>
</div>

<!-- BAD - Inconsistent indentation -->
<div class="container">
<h1>Title</h1>
   <p>Text</p>
</div>
```

### 5. Don't Change Class Names

Only change the content between tags, not the class names:

```html
<!-- ✓ CORRECT - Only change content -->
<h1 class="text-5xl font-bold">New Title</h1>

<!-- ✗ WRONG - Don't change class names -->
<h1 class="text-3xl">New Title</h1>
```

### 6. Always Include Full URLs for External Links

```html
<!-- ✓ CORRECT - Full URL -->
<a href="https://example.com/">Link</a>

<!-- ✗ WRONG - Missing https:// -->
<a href="example.com">Link</a>
```

### 7. Use Meaningful Alt Text for Images

```html
<!-- ✓ GOOD - Describes the image -->
<img src="products.jpg" alt="KCNails UKR nail products display">

<!-- ✗ BAD - Not descriptive -->
<img src="products.jpg" alt="image">
```

### 8. Keep SEO in Mind

Update meta tags when creating new pages:

```html
<meta name="description" content="Unique description for each page">
<meta name="keywords" content="relevant, keywords, here">
<title>Unique Title - KCNails UKR</title>
```

### 9. Test All Links After Updates

After updating links, test each one:

1. Navigation menu links
2. Footer links
3. Button links
4. Social media links
5. Email links

### 10. Document Your Changes

Keep notes of what you changed:

```
CHANGES LOG:
- Updated hero heading text
- Changed Shop Now link to https://new-shop.com
- Added Privacy Policy page
- Updated footer email to new@example.com
```

---

## Additional Resources

### Finding Icons

The page uses Font Awesome icons. Find more at:
- https://fontawesome.com/icons

### Finding SVG Icons

Alternative SVG icons (like the checkmark):
- https://heroicons.com/
- https://www.svgrepo.com/

### Tailwind CSS Classes

Full Tailwind documentation:
- https://tailwindcss.com/docs

### Color Palettes

Generate color schemes:
- https://colorhunt.co/
- https://coolors.co/

---

## Summary

You now have a comprehensive guide to maintain and customize the KCNails UKR landing page. Remember:

1. **Updating Text:** Change content between tags, keep classes the same
2. **Fixing Links:** Update `href` attributes to correct URLs
3. **Adding Policy Pages:** Create `privacy.html` and `terms.html` with provided templates
4. **Testing:** Always test changes on desktop, tablet, and mobile
5. **Backup:** Keep backups of original files

For questions or issues, refer to the troubleshooting sections or contact support at `iainhmunro@gmail.com`.

Happy customizing! 🎨