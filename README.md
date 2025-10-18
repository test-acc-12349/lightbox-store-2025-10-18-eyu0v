# Lightbox Store Landing Page - Maintenance & Customization Guide

A comprehensive guide for maintaining and customizing the Lightbox Store landing page, designed for developers of all skill levels.

---

## Table of Contents

1. [Overview](#overview)
2. [Understanding the Page Structure](#understanding-the-page-structure)
3. [Updating Text Content](#updating-text-content)
4. [Modifying Tailwind CSS Classes](#modifying-tailwind-css-classes)
5. [Fixing and Managing Links](#fixing-and-managing-links)
6. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
7. [Common Customization Tasks](#common-customization-tasks)
8. [Troubleshooting](#troubleshooting)
9. [Best Practices](#best-practices)

---

## Overview

The Lightbox Store landing page is a modern, responsive website built with:

- **HTML5** - Semantic markup structure
- **Tailwind CSS** - Utility-first CSS framework for styling
- **Font Awesome** - Icon library for visual elements
- **Vanilla JavaScript** - For interactive features (mobile menu, accordions)

### Key Features of This Landing Page:

- Sticky header navigation
- Mobile-responsive design
- Hero section with call-to-action
- Feature showcase cards
- Benefits section with alternating layouts
- Customer testimonials
- FAQ accordion section
- Contact form
- Comprehensive footer with links

### File Structure You'll Need:

```
your-project/
├── index.html          (main landing page)
├── privacy.html        (privacy policy - needs to be created)
├── terms.html          (terms of service - needs to be created)
└── blog.html           (blog page - needs to be created)
```

---

## Understanding the Page Structure

### Main Sections Breakdown

The landing page is organized into distinct sections, each with a unique ID for navigation:

| Section ID | Purpose | Location in HTML |
|-----------|---------|------------------|
| `#home` | Hero section with main CTA | Line ~200 |
| `#features` | Three feature cards (Portable, USB Power, Bright) | Line ~250 |
| `#benefits` | Three benefit cards (Low Cost, Free Shipping, Free Returns) | Line ~350 |
| `#about` | Company story and mission | Line ~550 |
| `#testimonials` | Customer reviews and ratings | Line ~620 |
| `#faq` | Frequently asked questions accordion | Line ~750 |
| `#contact` | Contact form and information | Line ~900 |

### Understanding Tailwind CSS Classes

This page uses Tailwind CSS, which means styling is applied through class names rather than traditional CSS. Here are the most important classes you'll encounter:

**Spacing Classes:**
- `py-24` = padding top and bottom of 24 units (6rem)
- `px-4` = padding left and right of 4 units (1rem)
- `mb-4` = margin bottom of 4 units (1rem)

**Responsive Classes:**
- `md:` prefix = applies only on medium screens and larger
- Example: `md:text-5xl` = text size 5xl on medium screens, smaller on mobile

**Color Classes:**
- `text-gray-900` = dark gray text
- `bg-white` = white background
- `text-white` = white text

**Layout Classes:**
- `flex` = flexbox display
- `grid` = grid display
- `grid-cols-1 md:grid-cols-3` = 1 column on mobile, 3 columns on medium+ screens

---

## Updating Text Content

### Finding and Changing Text

All text content in the landing page can be found and modified directly in the HTML. Here's how to locate and update specific sections:

### 1. Header/Navigation Text

**Location:** Lines 130-145 (Desktop Navigation)

**Current Code:**
```html
<a href="#home" class="nav-link text-gray-700 font-medium hover:text-gray-900">Home</a>
<a href="#features" class="nav-link text-gray-700 font-medium hover:text-gray-900">Features</a>
<a href="#benefits" class="nav-link text-gray-700 font-medium hover:text-gray-900">Benefits</a>
```

**How to Update:**
1. Find the section starting with `<!-- Desktop Navigation -->`
2. Change the text between the `<a>` tags
3. **Important:** Do NOT change the `href="#"` part - this controls where the link goes
4. Repeat the same changes in the `<!-- Mobile Menu -->` section (lines 158-165)

**Example - Adding a New Navigation Item:**
```html
<!-- Original -->
<a href="#faq" class="nav-link text-gray-700 font-medium hover:text-gray-900">FAQ</a>

<!-- Updated to add new section -->
<a href="#faq" class="nav-link text-gray-700 font-medium hover:text-gray-900">FAQ</a>
<a href="#gallery" class="nav-link text-gray-700 font-medium hover:text-gray-900">Gallery</a>
```

### 2. Announcement Bar Text

**Location:** Lines 173-175

**Current Code:**
```html
<div class="announcement-bar text-white text-center py-2 px-4 text-sm md:text-base">
    <i class="fas fa-truck mr-2"></i> Fast Worldwide Shipping - 5 Days Delivery | 100% Satisfaction Guarantee
</div>
```

**How to Update:**
Simply replace the text after the icon. Keep the `<i class="fas fa-truck mr-2"></i>` part unchanged.

**Example:**
```html
<!-- Updated announcement -->
<i class="fas fa-truck mr-2"></i> Free Shipping Worldwide | 30-Day Money-Back Guarantee
```

### 3. Hero Section Title and Subtitle

**Location:** Lines 195-210

**Current Code:**
```html
<h1 class="text-4xl md:text-6xl font-bold text-white mb-4 tracking-tight leading-tight">
    Lightbox Store
</h1>
<p class="text-xl md:text-2xl text-gray-100 mb-8 font-light leading-relaxed">
    Best Light LED Boxes
</p>
```

**How to Update:**
Replace the text between the tags. The classes control styling (size, color, spacing).

**Example:**
```html
<h1 class="text-4xl md:text-6xl font-bold text-white mb-4 tracking-tight leading-tight">
    Professional Lighting Solutions
</h1>
<p class="text-xl md:text-2xl text-gray-100 mb-8 font-light leading-relaxed">
    Premium LED Boxes for Content Creators
</p>
```

### 4. Feature Cards Section

**Location:** Lines 230-320

**Current Code Example:**
```html
<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4 tracking-tight">
    Premium Features
</h2>
<p class="text-lg text-gray-600 max-w-2xl mx-auto leading-relaxed">
    Discover what makes our LED light boxes the industry standard...
</p>
```

**How to Update Feature Card Content:**

Each feature card has this structure:
```html
<div class="feature-card bg-white border border-gray-200 rounded-xl p-8 hover:border-gray-300">
    <h3 class="text-2xl font-bold text-gray-900 mb-3">Portable</h3>
    <p class="text-gray-600 leading-relaxed mb-4">
        Lightweight and compact design makes it easy to carry...
    </p>
    <ul class="space-y-2 text-sm text-gray-600">
        <li><i class="fas fa-check text-green-600 mr-2"></i> Weighs less than 2 lbs</li>
        <li><i class="fas fa-check text-green-600 mr-2"></i> Fits in any bag or case</li>
    </ul>
</div>
```

**To customize:**
- Change the `<h3>` text (feature title)
- Change the `<p>` text (feature description)
- Change each `<li>` text (bullet points) - keep the `<i>` icon code unchanged

### 5. Benefits Section

**Location:** Lines 340-500

**How to Update Benefit Cards:**

Each benefit card has a heading and description:
```html
<h3 class="text-3xl md:text-4xl font-bold text-gray-900 mb-4">
    Unbeatable Pricing
</h3>
<p class="text-gray-600 text-lg leading-relaxed mb-4">
    We believe premium quality shouldn't come with a premium price tag...
</p>
```

Simply replace the text between the tags.

### 6. Testimonials Section

**Location:** Lines 650-750

**Current Structure:**
```html
<p class="text-gray-600 text-lg leading-relaxed mb-6">
    "The Lightbox LED boxes have completely transformed my photography business..."
</p>
<div class="border-t border-gray-200 pt-4">
    <p class="font-semibold text-gray-900">Sarah Mitchell</p>
    <p class="text-gray-600 text-sm">Professional Photographer, Creative Studios</p>
</div>
```

**To Update Testimonials:**
- Change the testimonial quote text
- Change the customer name
- Change the customer title/company

### 7. FAQ Content

**Location:** Lines 770-890

**Current Structure:**
```html
<button class="accordion-button w-full px-8 py-6 flex items-center justify-between...">
    <span class="text-lg font-semibold text-gray-900 text-left">
        What is the warranty coverage for Lightbox LED products?
    </span>
</button>
<div class="accordion-content">
    <div class="px-8 py-6 border-t border-gray-200 bg-gray-50">
        <p class="text-gray-600 leading-relaxed">
            All Lightbox Store LED light boxes come with a comprehensive 2-year...
        </p>
    </div>
</div>
```

**To Update FAQ:**
- Change the question text in the `<span>`
- Change the answer text in the `<p>` inside `.accordion-content`
- Do NOT modify the `class` attributes or structure

### 8. Footer Content

**Location:** Lines 950-1050

**Current Code Example:**
```html
<span class="text-2xl font-bold text-white">Lightbox</span>
<p class="text-sm text-gray-400 leading-relaxed mb-4">
    Premium LED light boxes for photographers, videographers...
</p>
```

**To Update Footer:**
- Change company name
- Change company description
- Update contact information

---

## Modifying Tailwind CSS Classes

### Understanding Responsive Design

This landing page uses a mobile-first approach with Tailwind CSS. Here's how the responsive prefixes work:

```html
<!-- Example: Text sizing that changes based on screen size -->
<h1 class="text-4xl md:text-6xl lg:text-7xl">
    Responsive Heading
</h1>
```

**What this means:**
- `text-4xl` = applies on mobile (smallest screens)
- `md:text-6xl` = applies on medium screens and larger (768px+)
- `lg:text-7xl` = applies on large screens and larger (1024px+)

### Common Tailwind Classes and What They Do

#### Text Styling

```html
<!-- Font size -->
<p class="text-sm">Small text</p>      <!-- 14px -->
<p class="text-base">Normal text</p>   <!-- 16px -->
<p class="text-lg">Large text</p>      <!-- 18px -->
<p class="text-2xl">Extra large</p>    <!-- 24px -->

<!-- Font weight -->
<p class="font-light">Light weight</p>      <!-- 300 -->
<p class="font-normal">Normal weight</p>    <!-- 400 -->
<p class="font-semibold">Semibold</p>       <!-- 600 -->
<p class="font-bold">Bold</p>               <!-- 700 -->

<!-- Text color -->
<p class="text-gray-600">Gray text</p>      <!-- Medium gray -->
<p class="text-blue-600">Blue text</p>      <!-- Medium blue -->
<p class="text-white">White text</p>        <!-- White -->
```

#### Spacing

```html
<!-- Padding (space inside) -->
<div class="p-4">All sides: 1rem</div>
<div class="px-4">Left and right: 1rem</div>
<div class="py-4">Top and bottom: 1rem</div>

<!-- Margin (space outside) -->
<div class="m-4">All sides: 1rem</div>
<div class="mx-4">Left and right: 1rem</div>
<div class="my-4">Top and bottom: 1rem</div>
<div class="mb-4">Bottom only: 1rem</div>
```

#### Colors

```html
<!-- Background colors -->
<div class="bg-white">White background</div>
<div class="bg-gray-50">Light gray background</div>
<div class="bg-gray-900">Dark gray background</div>
<div class="bg-blue-600">Blue background</div>

<!-- Text colors -->
<p class="text-gray-600">Gray text</p>
<p class="text-white">White text</p>
<p class="text-blue-600">Blue text</p>
```

#### Layout

```html
<!-- Flexbox -->
<div class="flex items-center justify-between">
    <!-- Items aligned center vertically, spaced between -->
</div>

<!-- Grid -->
<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
    <!-- 1 column on mobile, 3 columns on medium+ screens, 8 units gap -->
</div>

<!-- Borders and Rounded Corners -->
<div class="border border-gray-200 rounded-xl">
    <!-- 1px border, rounded corners -->
</div>
```

### How to Modify Specific Sections

#### Example 1: Making Feature Cards Larger

**Original:**
```html
<div class="feature-card bg-white border border-gray-200 rounded-xl p-8 hover:border-gray-300">
```

**To make padding larger:**
```html
<!-- Change p-8 to p-12 (larger padding) -->
<div class="feature-card bg-white border border-gray-200 rounded-xl p-12 hover:border-gray-300">
```

**Padding scale in Tailwind:**
- `p-4` = 1rem
- `p-6` = 1.5rem
- `p-8` = 2rem
- `p-12` = 3rem

#### Example 2: Changing Hero Section Background Color

**Original:**
```html
<section id="home" class="relative h-screen md:h-96 bg-cover bg-center...">
```

**To change the overlay darkness:**
Look for the `.hero-overlay` in the CSS section:
```css
.hero-overlay {
    background: linear-gradient(135deg, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.3) 100%);
}
```

The numbers `0.5` and `0.3` control opacity (0 = transparent, 1 = fully opaque):
```css
/* Darker overlay */
.hero-overlay {
    background: linear-gradient(135deg, rgba(0, 0, 0, 0.7) 0%, rgba(0, 0, 0, 0.5) 100%);
}

/* Lighter overlay */
.hero-overlay {
    background: linear-gradient(135deg, rgba(0, 0, 0, 0.3) 0%, rgba(0, 0, 0, 0.1) 100%);
}
```

#### Example 3: Changing Button Styling

**Original Button:**
```html
<a href="https://lru.com" class="cta-button text-white font-semibold px-8 py-4 rounded-lg inline-block text-lg">
    Shop Now <i class="fas fa-arrow-right ml-2"></i>
</a>
```

**To make buttons larger:**
```html
<!-- Increase padding: px-8 py-4 to px-10 py-5 -->
<a href="https://lru.com" class="cta-button text-white font-semibold px-10 py-5 rounded-lg inline-block text-lg">
    Shop Now <i class="fas fa-arrow-right ml-2"></i>
</a>
```

**To make text larger:**
```html
<!-- Change text-lg to text-xl -->
<a href="https://lru.com" class="cta-button text-white font-semibold px-8 py-4 rounded-lg inline-block text-xl">
    Shop Now <i class="fas fa-arrow-right ml-2"></i>
</a>
```

#### Example 4: Changing Grid Columns

**Original (3 columns on medium screens):**
```html
<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
```

**To make it 2 columns:**
```html
<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
```

**To make it 4 columns:**
```html
<div class="grid grid-cols-1 md:grid-cols-4 gap-8">
```

### Common Customization Patterns

#### Pattern 1: Adjust Section Spacing

**To add more space between sections:**
```html
<!-- Original: py-24 -->
<section class="py-24 px-4 sm:px-6 lg:px-8">

<!-- More space: py-32 -->
<section class="py-32 px-4 sm:px-6 lg:px-8">

<!-- Less space: py-16 -->
<section class="py-16 px-4 sm:px-6 lg:px-8">
```

#### Pattern 2: Change Heading Sizes

```html
<!-- Original -->
<h2 class="text-4xl md:text-5xl font-bold">Heading</h2>

<!-- Larger on desktop -->
<h2 class="text-4xl md:text-6xl font-bold">Heading</h2>

<!-- Smaller overall -->
<h2 class="text-3xl md:text-4xl font-bold">Heading</h2>
```

#### Pattern 3: Modify Card Shadows

```html
<!-- Original: shadow-md -->
<div class="bg-white rounded-xl shadow-md">

<!-- More shadow: shadow-lg -->
<div class="bg-white rounded-xl shadow-lg">

<!-- Subtle shadow: shadow-sm -->
<div class="bg-white rounded-xl shadow-sm">

<!-- No shadow -->
<div class="bg-white rounded-xl">
```

---

## Fixing and Managing Links

### Identifying All Links in the Page

The landing page contains three types of links:

1. **Internal Navigation Links** - Links to sections on the same page
2. **External Links** - Links to external websites
3. **Policy Links** - Links to privacy, terms, and blog pages

### 1. Navigation Links (Internal)

**Location:** Lines 130-145 (Desktop) and 158-165 (Mobile)

**Current Code:**
```html
<a href="#home" class="nav-link text-gray-700 font-medium hover:text-gray-900">Home</a>
<a href="#features" class="nav-link text-gray-700 font-medium hover:text-gray-900">Features</a>
<a href="#benefits" class="nav-link text-gray-700 font-medium hover:text-gray-900">Benefits</a>
<a href="#about" class="nav-link text-gray-700 font-medium hover:text-gray-900">About</a>
<a href="#testimonials" class="nav-link text-gray-700 font-medium hover:text-gray-900">Testimonials</a>
<a href="#faq" class="nav-link text-gray-700 font-medium hover:text-gray-900">FAQ</a>
<a href="#contact" class="nav-link text-gray-700 font-medium hover:text-gray-900">Contact</a>
```

**How These Work:**
- The `#` symbol means "link to a section on this page"
- `#home` links to the section with `id="home"`
- When clicked, the page smoothly scrolls to that section

**Checking if Links Work:**
1. Open the HTML file in your browser
2. Click each navigation link
3. The page should smoothly scroll to the corresponding section
4. If a link doesn't work, verify that the section ID exists on the page

**Example: Adding a New Navigation Link**

Step 1: Create a new section with an ID:
```html
<section id="gallery" class="py-24 px-4 sm:px-6 lg:px-8">
    <h2>Our Gallery</h2>
    <!-- Gallery content here -->
</section>
```

Step 2: Add the navigation link:
```html
<!-- In Desktop Navigation (after #faq) -->
<a href="#gallery" class="nav-link text-gray-700 font-medium hover:text-gray-900">Gallery</a>

<!-- In Mobile Menu (after #faq) -->
<a href="#gallery" class="text-gray-700 font-medium hover:text-gray-900 block py-2">Gallery</a>
```

### 2. Call-to-Action (CTA) Links - External

**Locations:** Lines 150, 210, 280, 365, 430, 495, 560, 905, 930

**Current Code Examples:**
```html
<a href="https://lru.com" class="hidden sm:inline-block cta-button text-white font-semibold px-6 py-2 rounded-lg">
    Buy Now
</a>
```

**What This Link Does:**
- `href="https://lru.com"` = When clicked, opens https://lru.com in the same window
- This is where customers go to actually purchase products

**How to Update External Links:**

Step 1: Find all instances of `https://lru.com`
- Use keyboard shortcut: `Ctrl+F` (Windows) or `Cmd+F` (Mac)
- Search for: `lru.com`
- This will highlight all instances

Step 2: Replace with your actual shop URL:
```html
<!-- Original -->
<a href="https://lru.com" class="cta-button...">Buy Now</a>

<!-- Updated -->
<a href="https://your-shop-url.com" class="cta-button...">Buy Now</a>
```

**Important:** Keep the `https://` part - this tells the browser it's a web address.

**All CTA Links to Update:**

| Line # | Current Link | Section |
|--------|-------------|---------|
| 150 | `https://lru.com` | Header "Buy Now" button |
| 165 | `https://lru.com` | Mobile menu "Buy Now" |
| 210 | `https://lru.com` | Hero section "Shop Now" |
| 280 | `https://lru.com` | Feature section "View Pricing" |
| 365 | `https://lru.com` | Benefits "Shop Now" |
| 430 | `https://lru.com` | Benefits "Learn More" |
| 495 | `https://lru.com` | Benefits "Learn More" |
| 560 | `https://lru.com` | CTA section "Shop Collection" |
| 905 | `https://lru.com` | Contact "Shop Our Collection" |

### 3. Policy and Blog Links

**Locations:** Lines 400-410, 430, 1000-1010

**Current Code:**
```html
<a href="privacy.html" class="text-gray-400 hover:text-white...">Privacy Policy</a>
<a href="terms.html" class="text-gray-400 hover:text-white...">Terms of Service</a>
<a href="blog.html" class="text-gray-400 hover:text-white...">Blog</a>
```

**These links reference files that need to be created:**
- `privacy.html` - Privacy policy page
- `terms.html` - Terms of service page
- `blog.html` - Blog page

**Status:** These files are currently referenced but don't exist yet. See the next section for creating them.

### 4. Contact Links

**Location:** Lines 885-890

**Current Code:**
```html
<a href="mailto:admin@lru.com" class="text-blue-600 hover:text-blue-700...">
    admin@lru.com
</a>
```

**How to Update Email:**
```html
<!-- Original -->
<a href="mailto:admin@lru.com">admin@lru.com</a>

<!-- Updated -->
<a href="mailto:your-email@yourdomain.com">your-email@yourdomain.com</a>
```

**How to Update Website URL:**
```html
<!-- Original -->
<a href="https://lru.com" class="text-green-600 hover:text-green-700...">
    https://lru.com
</a>

<!-- Updated -->
<a href="https://your-website.com" class="text-green-600 hover:text-green-700...">
    https://your-website.com
</a>
```

### 5. Social Media Links

**Location:** Lines 970-985

**Current Code:**
```html
<a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
    <i class="fab fa-facebook-f text-lg"></i>
</a>
```

**How to Update Social Links:**
```html
<!-- Original (placeholder) -->
<a href="#" class="text-gray-400 hover:text-white...">
    <i class="fab fa-facebook-f text-lg"></i>
</a>

<!-- Updated with real Facebook URL -->
<a href="https://facebook.com/your-page" class="text-gray-400 hover:text-white..." target="_blank">
    <i class="fab fa-facebook-f text-lg"></i>
</a>
```

**Social Media Links to Update:**

```html
<!-- Facebook -->
<a href="https://facebook.com/your-page" target="_blank">
    <i class="fab fa-facebook-f text-lg"></i>
</a>

<!-- Twitter -->
<a href="https://twitter.com/your-handle" target="_blank">
    <i class="fab fa-twitter text-lg"></i>
</a>

<!-- Instagram -->
<a href="https://instagram.com/your-profile" target="_blank">
    <i class="fab fa-instagram text-lg"></i>
</a>

<!-- YouTube -->
<a href="https://youtube.com/your-channel" target="_blank">
    <i class="fab fa-youtube text-lg"></i>
</a>
```

**Important:** Add `target="_blank"` to open social links in a new tab.

### Link Update Checklist

Use this checklist to ensure all links are updated:

```
EXTERNAL LINKS (Shop/CTA):
☐ Header "Buy Now" button (line 150)
☐ Mobile menu "Buy Now" (line 165)
☐ Hero "Shop Now" (line 210)
☐ Features "View Pricing" (line 280)
☐ Benefits "Shop Now" (line 365)
☐ Benefits "Learn More" (line 430)
☐ Benefits "Learn More" (line 495)
☐ CTA section "Shop Collection" (line 560)
☐ Contact "Shop Collection" (line 905)

CONTACT LINKS:
☐ Email address (line 885)
☐ Website URL (line 890)

SOCIAL MEDIA:
☐ Facebook (line 970)
☐ Twitter (line 975)
☐ Instagram (line 980)
☐ YouTube (line 985)

POLICY LINKS:
☐ Privacy Policy (line 1000)
☐ Terms of Service (line 1005)
☐ Blog (line 1010)
```

---

## Linking Privacy and Terms Pages

### Creating Required Files

You need to create three new HTML files in the same folder as your `index.html`:

1. `privacy.html` - Privacy Policy page
2. `terms.html` - Terms of Service page
3. `blog.html` - Blog page (optional but referenced)

### Step-by-Step: Creating privacy.html

**Step 1:** Create a new file named `privacy.html` in the same folder as `index.html`

**Step 2:** Copy this complete template into `privacy.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Privacy Policy - Lightbox Store">
    <title>Privacy Policy - Lightbox Store</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
        }
        
        .header-sticky {
            position: sticky;
            top: 0;
            z-index: 50;
            background: white;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body class="bg-white text-gray-900">
    <!-- Header -->
    <header class="header-sticky">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex items-center justify-between">
            <div class="flex items-center space-x-2 cursor-pointer">
                <i class="fas fa-lightbulb text-2xl text-gray-900"></i>
                <a href="index.html" class="text-2xl font-bold text-gray-900">Lightbox</a>
            </div>
            <a href="index.html" class="text-gray-700 font-medium hover:text-gray-900">
                <i class="fas fa-arrow-left mr-2"></i>Back to Home
            </a>
        </nav>
    </header>

    <!-- Privacy Policy Content -->
    <section class="py-16 px-4 sm:px-6 lg:px-8">
        <div class="max-w-4xl mx-auto">
            <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Privacy Policy</h1>
            
            <div class="prose prose-lg text-gray-600 space-y-8 max-w-none">
                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">1. Introduction</h2>
                    <p>
                        Lightbox Store ("we," "us," "our," or "Company") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you visit our website.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">2. Information We Collect</h2>
                    <p>We may collect information about you in a variety of ways. The information we may collect on the site includes:</p>
                    <ul class="list-disc list-inside space-y-2 mt-4">
                        <li><strong>Personal Data:</strong> Name, email address, phone number, shipping address</li>
                        <li><strong>Payment Information:</strong> Credit card details (processed securely)</li>
                        <li><strong>Usage Data:</strong> Browser type, IP address, pages visited, time spent on pages</li>
                        <li><strong>Cookies:</strong> Information stored on your device for website functionality</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">3. Use of Your Information</h2>
                    <p>Having accurate information about you permits us to provide you with a smooth, efficient, and customized experience. Specifically, we may use information collected about you via the site to:</p>
                    <ul class="list-disc list-inside space-y-2 mt-4">
                        <li>Process your transactions and send related information</li>
                        <li>Generate a personal profile about you</li>
                        <li>Increase the efficiency and operation of the site</li>
                        <li>Monitor and analyze usage and trends to improve your experience</li>
                        <li>Notify you of updates to the site</li>
                        <li>Send marketing communications (with your consent)</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">4. Disclosure of Your Information</h2>
                    <p>We may share your information in the following situations:</p>
                    <ul class="list-disc list-inside space-y-2 mt-4">
                        <li>With service providers who assist us in operating our website</li>
                        <li>With payment processors to process your transactions</li>
                        <li>When required by law or to protect our legal rights</li>
                        <li>With your consent for other purposes</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">5. Security of Your Information</h2>
                    <p>
                        We use administrative, technical, and physical security measures to protect your personal information. However, perfect security does not exist on the Internet. If you have any questions about the security of your personal information, please contact us.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">6. Contact Us</h2>
                    <p>If you have questions or comments about this Privacy Policy, please contact us at:</p>
                    <p class="mt-4">
                        <strong>Email:</strong> <a href="mailto:admin@lru.com" class="text-blue-600 hover:text-blue-700">admin@lru.com</a><br>
                        <strong>Website:</strong> <a href="https://lru.com" class="text-blue-600 hover:text-blue-700">https://lru.com</a>
                    </p>
                </div>

                <div class="bg-gray-50 p-6 rounded-lg mt-8">
                    <p class="text-sm text-gray-600">
                        <strong>Last Updated:</strong> January 2024<br>
                        This Privacy Policy is effective and will remain in effect except with respect to any changes in its provisions in the future, which will be in effect immediately upon posting to the site.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-16 px-4 sm:px-6 lg:px-8 mt-16">
        <div class="max-w-7xl mx-auto text-center">
            <p class="text-sm text-gray-400 mb-4">
                &copy; 2024 Lightbox Store. All rights reserved.
            </p>
            <div class="space-x-4">
                <a href="index.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Home</a>
                <a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Privacy Policy</a>
                <a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Terms of Service</a>
            </div>
        </div>
    </footer>
</body>
</html>
```

### Step-by-Step: Creating terms.html

**Step 1:** Create a new file named `terms.html`

**Step 2:** Copy this complete template into `terms.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Terms of Service - Lightbox Store">
    <title>Terms of Service - Lightbox Store</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
        }
        
        .header-sticky {
            position: sticky;
            top: 0;
            z-index: 50;
            background: white;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body class="bg-white text-gray-900">
    <!-- Header -->
    <header class="header-sticky">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex items-center justify-between">
            <div class="flex items-center space-x-2 cursor-pointer">
                <i class="fas fa-lightbulb text-2xl text-gray-900"></i>
                <a href="index.html" class="text-2xl font-bold text-gray-900">Lightbox</a>
            </div>
            <a href="index.html" class="text-gray-700 font-medium hover:text-gray-900">
                <i class="fas fa-arrow-left mr-2"></i>Back to Home
            </a>
        </nav>
    </header>

    <!-- Terms of Service Content -->
    <section class="py-16 px-4 sm:px-6 lg:px-8">
        <div class="max-w-4xl mx-auto">
            <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-8">Terms of Service</h1>
            
            <div class="prose prose-lg text-gray-600 space-y-8 max-w-none">
                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">1. Agreement to Terms</h2>
                    <p>
                        By accessing and using this website, you accept and agree to be bound by the terms and provision of this agreement. If you do not agree to abide by the above, please do not use this service.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">2. Use License</h2>
                    <p>
                        Permission is granted to temporarily download one copy of the materials (information or software) on Lightbox Store's website for personal, non-commercial transitory viewing only. This is the grant of a license, not a transfer of title, and under this license you may not:
                    </p>
                    <ul class="list-disc list-inside space-y-2 mt-4">
                        <li>Modifying or copying the materials</li>
                        <li>Using the materials for any commercial purpose or for any public display</li>
                        <li>Attempting to decompile or reverse engineer any software contained on the website</li>
                        <li>Removing any copyright or other proprietary notations from the materials</li>
                        <li>Transferring the materials to another person or "mirroring" the materials on any other server</li>
                    </ul>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">3. Disclaimer</h2>
                    <p>
                        The materials on Lightbox Store's website are provided on an 'as is' basis. Lightbox Store makes no warranties, expressed or implied, and hereby disclaims and negates all other warranties including, without limitation, implied warranties or conditions of merchantability, fitness for a particular purpose, or non-infringement of intellectual property or other violation of rights.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">4. Limitations</h2>
                    <p>
                        In no event shall Lightbox Store or its suppliers be liable for any damages (including, without limitation, damages for loss of data or profit, or due to business interruption) arising out of the use or inability to use the materials on Lightbox Store's website.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">5. Accuracy of Materials</h2>
                    <p>
                        The materials appearing on Lightbox Store's website could include technical, typographical, or photographic errors. Lightbox Store does not warrant that any of the materials on its website are accurate, complete, or current. Lightbox Store may make changes to the materials contained on its website at any time without notice.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">6. Links</h2>
                    <p>
                        Lightbox Store has not reviewed all of the sites linked to its website and is not responsible for the contents of any such linked site. The inclusion of any link does not imply endorsement by Lightbox Store of the site. Use of any such linked website is at the user's own risk.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">7. Modifications</h2>
                    <p>
                        Lightbox Store may revise these terms of service for its website at any time without notice. By using this website, you are agreeing to be bound by the then current version of these terms of service.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">8. Governing Law</h2>
                    <p>
                        These terms and conditions are governed by and construed in accordance with the laws of the jurisdiction in which Lightbox Store operates, and you irrevocably submit to the exclusive jurisdiction of the courts in that location.
                    </p>
                </div>

                <div>
                    <h2 class="text-2xl font-bold text-gray-900 mb-4">9. Contact Information</h2>
                    <p>If you have any questions about these Terms of Service, please contact us at:</p>
                    <p class="mt-4">
                        <strong>Email:</strong> <a href="mailto:admin@lru.com" class="text-blue-600 hover:text-blue-700">admin@lru.com</a><br>
                        <strong>Website:</strong> <a href="https://lru.com" class="text-blue-600 hover:text-blue-700">https://lru.com</a>
                    </p>
                </div>

                <div class="bg-gray-50 p-6 rounded-lg mt-8">
                    <p class="text-sm text-gray-600">
                        <strong>Last Updated:</strong> January 2024<br>
                        These Terms of Service are effective and will remain in effect except with respect to any changes in its provisions in the future, which will be in effect immediately upon posting to the site.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-16 px-4 sm:px-6 lg:px-8 mt-16">
        <div class="max-w-7xl mx-auto text-center">
            <p class="text-sm text-gray-400 mb-4">
                &copy; 2024 Lightbox Store. All rights reserved.
            </p>
            <div class="space-x-4">
                <a href="index.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Home</a>
                <a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Privacy Policy</a>
                <a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Terms of Service</a>
            </div>
        </div>
    </footer>
</body>
</html>
```

### Step-by-Step: Creating blog.html

**Step 1:** Create a new file named `blog.html`

**Step 2:** Copy this complete template into `blog.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Blog - Lightbox Store">
    <title>Blog - Lightbox Store</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
        }
        
        .header-sticky {
            position: sticky;
            top: 0;
            z-index: 50;
            background: white;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body class="bg-white text-gray-900">
    <!-- Header -->
    <header class="header-sticky">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex items-center justify-between">
            <div class="flex items-center space-x-2 cursor-pointer">
                <i class="fas fa-lightbulb text-2xl text-gray-900"></i>
                <a href="index.html" class="text-2xl font-bold text-gray-900">Lightbox</a>
            </div>
            <a href="index.html" class="text-gray-700 font-medium hover:text-gray-900">
                <i class="fas fa-arrow-left mr-2"></i>Back to Home
            </a>
        </nav>
    </header>

    <!-- Blog Content -->
    <section class="py-16 px-4 sm:px-6 lg:px-8">
        <div class="max-w-6xl mx-auto">
            <div class="mb-12">
                <h1 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">Lightbox Blog</h1>
                <p class="text-lg text-gray-600">Tips, tutorials, and insights for content creators and photographers</p>
            </div>

            <!-- Blog Posts Grid -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Blog Post 1 -->
                <article class="bg-white border border-gray-200 rounded-xl overflow-hidden hover:shadow-lg transition-shadow duration-300">
                    <div class="h-48 bg-gradient-to-br from-blue-400 to-blue-600 flex items-center justify-center">
                        <i class="fas fa-lightbulb text-white text-6xl"></i>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Getting Started with LED Lighting</h3>
                        <p class="text-gray-600 text-sm mb-4">Learn the basics of LED lighting and how to choose the right setup for your needs.</p>
                        <div class="flex items-center justify-between">
                            <span class="text-gray-500 text-sm">January 15, 2024</span>
                            <a href="#" class="text-blue-600 hover:text-blue-700 font-semibold">Read More →</a>
                        </div>
                    </div>
                </article>

                <!-- Blog Post 2 -->
                <article class="bg-white border border-gray-200 rounded-xl overflow-hidden hover:shadow-lg transition-shadow duration-300">
                    <div class="h-48 bg-gradient-to-br from-green-400 to-green-600 flex items-center justify-center">
                        <i class="fas fa-camera text-white text-6xl"></i>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Photography Tips & Tricks</h3>
                        <p class="text-gray-600 text-sm mb-4">Professional photography techniques to elevate your content and impress your audience.</p>
                        <div class="flex items-center justify-between">
                            <span class="text-gray-500 text-sm">January 10, 2024</span>
                            <a href="#" class="text-blue-600 hover:text-blue-700 font-semibold">Read More →</a>
                        </div>
                    </div>
                </article>

                <!-- Blog Post 3 -->
                <article class="bg-white border border-gray-200 rounded-xl overflow-hidden hover:shadow-lg transition-shadow duration-300">
                    <div class="h-48 bg-gradient-to-br from-purple-400 to-purple-600 flex items-center justify-center">
                        <i class="fas fa-video text-white text-6xl"></i>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Video Production Best Practices</h3>
                        <p class="text-gray-600 text-sm mb-4">Master the art of video production with our comprehensive guide to lighting and setup.</p>
                        <div class="flex items-center justify-between">
                            <span class="text-gray-500 text-sm">January 5, 2024</span>
                            <a href="#" class="text-blue-600 hover:text-blue-700 font-semibold">Read More →</a>
                        </div>
                    </div>
                </article>
            </div>

            <!-- Coming Soon Message -->
            <div class="mt-16 bg-gray-50 rounded-xl p-8 text-center">
                <h3 class="text-2xl font-bold text-gray-900 mb-2">More Content Coming Soon!</h3>
                <p class="text-gray-600">We're working on more helpful articles and tutorials. Check back soon for updates.</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-300 py-16 px-4 sm:px-6 lg:px-8 mt-16">
        <div class="max-w-7xl mx-auto text-center">
            <p class="text-sm text-gray-400 mb-4">
                &copy; 2024 Lightbox Store. All rights reserved.
            </p>
            <div class="space-x-4">
                <a href="index.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Home</a>
                <a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Privacy Policy</a>
                <a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300 text-sm">Terms of Service</a>
            </div>
        </div>
    </footer>
</body>
</html>
```

### Verifying Links Work

After creating the three new files, verify that all links work:

**Step 1:** Open `index.html` in your browser

**Step 2:** Test these links:
- Footer: Click "Privacy Policy" → should open `privacy.html`
- Footer: Click "Terms of Service" → should open `terms.html`
- Footer: Click "Blog" → should open `blog.html`
- On each new page: Click "Back to Home" → should return to `index.html`

**Step 3:** If links don't work, verify:
- All files are in the same folder
- File names are spelled exactly: `privacy.html`, `terms.html`, `blog.html`
- The `href` attributes match the file names exactly

### Customizing Policy Pages

You can customize the content of each policy page:

**In privacy.html:**
- Update email address (line 85): `admin@lru.com`
- Update website URL (line 87): `https://lru.com`
- Update "Last Updated" date (line 122)
- Add your specific privacy practices in each section

**In terms.html:**
- Update email address (line 107): `admin@lru.com`
- Update website URL (line 109): `https://lru.com`
- Update "Last Updated" date (line 144)
- Customize terms to match your business practices

**In blog.html:**
- Add real blog posts by duplicating the blog post template
- Update post titles, descriptions, dates, and links
- Add featured images if desired

---

## Common Customization Tasks

### Task 1: Change Brand Name Throughout

To change "Lightbox Store" to your brand name:

**Step 1:** Use Find & Replace
- Press `Ctrl+H` (Windows) or `Cmd+Option+F` (Mac)
- Find: `Lightbox Store`
- Replace with: `Your Brand Name`
- Click "Replace All"

**Step 2:** Update logo text
- Line 128: `<span class="text-2xl font-bold text-gray-900">Lightbox</span>`
- Change to: `<span class="text-2xl font-bold text-gray-900">Your Brand</span>`

**Step 3:** Update page titles
- Line 9: `<title>Lightbox Store - Best Light LED Boxes</title>`
- Change to: `<title>Your Brand - Your Tagline</title>`

### Task 2: Change Hero Section Background Image

**Current:**
```html
<section id="home" class="relative h-screen md:h-96 bg-cover bg-center flex items-center justify-center" 
    style="background-image: url('https://images.unsplash.com/photo-1504093376055-b3094b674dcb?w=1600&h=900&fit=crop&q=80');">
```

**To change:**
1. Find a new image URL from Unsplash, Pexels, or your own server
2. Replace the URL in the `style` attribute:
```html
style="background-image: url('YOUR-NEW-IMAGE-URL-HERE');"
```

**Example with your own image:**
```html
style="background-image: url('images/hero-background.jpg');"
```

### Task 3: Add New Feature Card

**Step 1:** Find the features section (line ~250)

**Step 2:** Copy an existing feature card:
```html
<div class="feature-card bg-white border border-gray-200 rounded-xl p-8 hover:border-gray-300">
    <div class="bg-gradient-to-br from-blue-50 to-blue-100 w-16 h-16 rounded-lg flex items-center justify-center mb-6">
        <i class="fas fa-briefcase text-2xl text-blue-600"></i>
    </div>
    <h3 class="text-2xl font-bold text-gray-900 mb-3">Portable</h3>
    <p class="text-gray-600 leading-relaxed mb-4">
        Lightweight and compact design...
    </p>
    <ul class="space-y-2 text-sm text-gray-600">
        <li><i class="fas fa-check text-green-600 mr-2"></i> Weighs less than 2 lbs</li>
    </ul>
</div>
```

**Step 3:** Paste it after the last feature card and customize:
- Change the icon (find at fontawesome.com)
- Change the title
- Change the description
- Change the bullet points

**Step 4:** Update the grid to accommodate more cards:
```html
<!-- Original: 3 columns -->
<div class="grid grid-cols-1 md:grid-cols-3 gap-8">

<!-- For 4 cards: -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
```

### Task 4: Modify Testimonial

**Step 1:** Find testimonials section (line ~650)

**Step 2:** Update testimonial text:
```html
<!-- Original -->
<p class="text-gray-600 text-lg leading-relaxed mb-6">
    "The Lightbox LED boxes have completely transformed my photography business..."
</p>

<!-- Updated -->
<p class="text-gray-600 text-lg leading-relaxed mb-6">
    "Your new testimonial text here. Make it specific and authentic."
</p>
```

**Step 3:** Update customer information:
```html
<!-- Original -->
<p class="font-semibold text-gray-900">Sarah Mitchell</p>
<p class="text-gray-600 text-sm">Professional Photographer, Creative Studios</p>

<!-- Updated -->
<p class="font-semibold text-gray-900">Customer Name</p>
<p class="text-gray-600 text-sm">Job Title, Company Name</p>
```

### Task 5: Change Color Scheme

The main colors used are in the CSS section. To change from dark gray/black to another color:

**Find the CTA button style (line ~65):**
```css
.cta-button {
    background: linear-gradient(135deg, #1f2937 0%, #111827 100%);
}
```

**Change to different colors:**
```css
/* Blue theme */
.cta-button {
    background: linear-gradient(135deg, #2563eb 0%, #1d4ed8 100%);
}

/* Green theme */
.cta-button {
    background: linear-gradient(135deg, #059669 0%, #047857 100%);
}

/* Purple theme */
.cta-button {
    background: linear-gradient(135deg, #7c3aed 0%, #6d28d9 100%);
}
```

### Task 6: Add Newsletter Signup

**Step 1:** Find a good location (usually before footer)

**Step 2:** Add this section:
```html
<!-- Newsletter Section -->
<section class="py-16 px-4 sm:px-6 lg:px-8 bg-gradient-to-r from-blue-600 to-blue-800 text-white">
    <div class="max-w-2xl mx-auto text-center">
        <h2 class="text-3xl font-bold mb-4">Subscribe to Our Newsletter</h2>
        <p class="text-blue-100 mb-8">Get the latest tips and updates delivered to your inbox</p>
        <form class="flex flex-col sm:flex-row gap-4">
            <input 
                type="email" 
                placeholder="Enter your email" 
                class="flex-1 px-4 py-3 rounded-lg text-gray-900 focus:outline-none"
                required
            >
            <button 
                type="submit" 
                class="bg-white text-blue-600 font-semibold px-8 py-3 rounded-lg hover:bg-gray-100 transition-colors duration-300"
            >
                Subscribe
            </button>
        </form>
    </div>
</section>
```

---

## Troubleshooting

### Issue: Links Not Working

**Symptom:** Clicking a link does nothing or gives an error

**Solutions:**

1. **For internal links (#home, #features):**
   - Verify the section has the correct ID attribute
   - Example: `<section id="home">` must exist for `href="#home"` to work
   - Check spelling matches exactly (case-sensitive)

2. **For external links:**
   - Verify the URL includes `https://`
   - Test the URL in a new browser tab
   - Check for typos in the domain name

3. **For file links (privacy.html, terms.html):**
   - Verify files exist in the same folder as index.html
   - Check file names match exactly
   - Use forward slashes: `href="privacy.html"` not `href="/privacy.html"`

**Testing Checklist:**
```
☐ Is the link's href attribute correct?
☐ Does the target section/file exist?
☐ Is the file name spelled correctly?
☐ Are all files in the same folder?
☐ Does the URL include https:// for external links?
```

### Issue: Styling Looks Wrong

**Symptom:** Colors, spacing, or layout is incorrect

**Solutions:**

1. **Clear browser cache:**
   - Press `Ctrl+Shift+Delete` (Windows) or `Cmd+Shift+Delete` (Mac)
   - Clear all cached files
   - Reload the page

2. **Check Tailwind CSS is loading:**
   - Open browser DevTools (F12)
   - Go to Network tab
   - Reload page
   - Look for `cdn.tailwindcss.com` - should show status 200
   - If not loading, check internet connection

3. **Verify class names are correct:**
   - Tailwind classes must be exact: `text-gray-600` not `text-gray-60`
   - Check for typos in class names
   - Use only valid Tailwind classes

### Issue: Mobile Menu Not Working

**Symptom:** Mobile menu doesn't open when clicking hamburger icon

**Solutions:**

1. **Check JavaScript is enabled:**
   - Some browsers have JavaScript disabled
   - Enable it in browser settings

2. **Verify menu button class:**
   - Find: `class="mobile-menu-button"`
   - Should be on line ~150

3. **Check mobile menu div:**
   - Find: `class="mobile-menu hidden md:hidden"`
   - Should exist on line ~156

4. **Test on actual mobile device:**
   - Use browser DevTools responsive mode
   - Press `Ctrl+Shift+M` to toggle mobile view

### Issue: Images Not Loading

**Symptom:** Broken image icons appear instead of images

**Solutions:**

1. **For external images (Unsplash):**
   - Check internet connection
   - Verify URL is correct
   - Try a different image URL
   - Check if the image URL has expired

2. **For local images:**
   - Verify image file exists in project folder
   - Check file name matches exactly
   - Use correct file path: `images/photo.jpg` not `Images/photo.jpg`
   - Use forward slashes, not backslashes

3. **Test image URL:**
   - Copy the URL and open in new browser tab
   - If image doesn't load there, the URL is broken

### Issue: Accordion Not Expanding

**Symptom:** FAQ accordion buttons don't expand when clicked

**Solutions:**

1. **Verify JavaScript is enabled:**
   - Check browser JavaScript is enabled

2. **Check accordion structure:**
   - Each Q&A must have this structure:
   ```html
   <button class="accordion-button">Question</button>
   <div class="accordion-content">Answer</div>
   ```

3. **Verify function is defined:**
   - Find `function toggleAccordion(this)` in script section
   - Should be around line 1040

### Issue: Form Not Submitting

**Symptom:** Contact form doesn't submit or shows error

**Solutions:**

1. **Check form has required fields:**
   - All inputs should have `required` attribute
   - Email input should have `type="email"`

2. **Verify form structure:**
   - Form must have `<form>` tags
   - Submit button must have `type="submit"`

3. **Check browser console:**
   - Press F12 to open DevTools
   - Go to Console tab
   - Look for error messages
   - Screenshot errors and search for solutions

### Issue: Page Loads Slowly

**Symptom:** Page takes a long time to load

**Solutions:**

1. **Check image sizes:**
   - Large images slow down loading
   - Compress images before using
   - Use image optimization tools

2. **Minimize external resources:**
   - Reduce number of external stylesheets
   - Combine CSS files if possible
   - Use local fonts instead of external

3. **Test on different connection:**
   - Try on faster internet
   - Test on mobile data
   - Use browser DevTools Network tab to identify slow-loading resources

### Issue: Responsive Design Broken

**Symptom:** Layout doesn't adapt properly on mobile

**Solutions:**

1. **Check viewport meta tag:**
   - Should be on line 3: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
   - If missing, add it

2. **Test with DevTools:**
   - Press `Ctrl+Shift+M` to toggle device mode
   - Test on different screen sizes
   - Check that md: and lg: classes work correctly

3. **Verify responsive classes:**
   - Classes should include breakpoints: `md:`, `lg:`
   - Example: `grid-cols-1 md:grid-cols-3`
   - Not: `grid-cols-3` (only desktop size)

---

## Best Practices

### 1. Always Backup Before Making Changes

Before making significant changes:
```
1. Create a copy of index.html named index-backup.html
2. Make changes to the original
3. If something breaks, you have the backup
```

### 2. Use Version Control (Git)

If you know Git:
```bash
git init
git add .
git commit -m "Initial landing page"
git add index.html
git commit -m "Updated hero section text"
```

### 3. Test Changes in Multiple Browsers

After making changes, test in:
- Chrome
- Firefox
- Safari
- Edge

### 4. Test on Mobile Devices

Use DevTools responsive mode:
- Press `Ctrl+Shift+M`
- Test on iPhone, iPad, Android sizes
- Check touch interactions work

### 5. Keep Links Updated

When updating links:
- Create a spreadsheet tracking all URLs
- Update both desktop and mobile versions
- Test each link after updating

### 6. Validate HTML

Use an HTML validator:
- Visit: https://validator.w3.org/
- Upload your HTML file
- Fix any errors reported

### 7. Optimize Images

Before adding images:
- Compress using tools like TinyPNG
- Use appropriate file format (JPG for photos, PNG for graphics)
- Resize to actual display size

### 8. Keep Consistent Styling

When modifying styles:
- Use existing Tailwind classes
- Don't create custom CSS unless necessary
- Maintain spacing consistency (multiples of 4)
- Use the existing color palette

### 9. Document Your Changes

Add comments to track modifications:
```html
<!-- Updated: 2024-01-15 - Changed hero text -->
<h1 class="text-4xl md:text-6xl font-bold text-white mb-4">
    New Hero Title
</h1>
```

### 10. Regular Maintenance Checklist

Perform these checks monthly:
```
☐ Test all links work
☐ Check images load correctly
☐ Verify form submissions work
☐ Test on mobile devices
☐ Check page loading speed
☐ Review and update outdated content
☐ Backup current version
☐ Check browser console for errors
☐ Verify responsive design
☐ Test contact form functionality
```

---

## Quick Reference Guide

### File Locations for Common Updates

| Task | File | Lines |
|------|------|-------|
| Change navigation links | index.html | 130-165 |
| Update hero section | index.html | 195-210 |
| Modify feature cards | index.html | 250-320 |
| Update benefits section | index.html | 340-500 |
| Change testimonials | index.html | 650-750 |
| Update FAQ | index.html | 770-890 |
| Modify footer | index.html | 950-1050 |
| Update email | index.html, privacy.html, terms.html | Multiple |
| Change brand name | All files | Search & Replace |

### Useful Tailwind CSS Shortcuts

```html
<!-- Spacing -->
py-24 = padding top/bottom: 6rem
px-4 = padding left/right: 1rem
mb-4 = margin bottom: 1rem

<!-- Text -->
text-4xl = font size: 2.25rem
font-bold = font weight: 700
text-gray-600 = gray text color

<!-- Layout -->
grid-cols-3 = 3 column grid
md:grid-cols-2 = 2 columns on medium+ screens
flex = flexbox layout
items-center = vertical center alignment

<!-- Colors -->
bg-white = white background
text-white = white text
bg-gray-900 = dark background
```

### Common Icon Names (Font Awesome)

```html
<i class="fas fa-lightbulb"></i>          <!-- Lightbulb -->
<i class="fas fa-briefcase"></i>          <!-- Briefcase -->
<i class="fas fa-plug"></i>               <!-- Plug -->
<i class="fas fa-sun"></i>                <!-- Sun -->
<i class="fas fa-check"></i>              <!-- Checkmark -->
<i class="fas fa-arrow-right"></i>        <!-- Arrow right -->
<i class="fas fa-truck"></i>              <!-- Truck -->
<i class="fas fa-star"></i>               <!-- Star -->
<i class="fas fa-envelope"></i>           <!-- Envelope -->
<i class="fas fa-globe"></i>              <!-- Globe -->
```

Find more at: https://fontawesome.com/icons

---

## Support Resources

### Learning Resources

- **Tailwind CSS Documentation:** https://tailwindcss.com/docs
- **HTML Tutorial:** https://developer.mozilla.org/en-US/docs/Web/HTML
- **CSS Basics:** https://developer.mozilla.org/en-US/docs/Web/CSS
- **Font Awesome Icons:** https://fontawesome.com/icons
- **Unsplash Images:** https://unsplash.com

### Tools

- **Browser DevTools:** Press F12 to inspect elements
- **HTML Validator:** https://validator.w3.org/
- **Image Compressor:** https://tinypng.com/
- **Color Picker:** https://www.colorpicker.com/
- **Responsive Design Tester:** https://responsivedesignchecker.com/

### Getting Help

When you encounter issues:
1. Check the Troubleshooting section above
2. Search the error message on Google
3. Check Stack Overflow for similar issues
4. Ask in web development communities like Reddit r/webdev

---

## Summary

This landing page is built with modern, maintainable code using Tailwind CSS. Key takeaways:

- **Text updates** are straightforward - just change the text between HTML tags
- **Styling changes** use Tailwind utility classes - learn the common ones
- **Links need verification** - test after updating
- **Create policy pages** using the provided templates
- **Always backup** before making significant changes
- **Test on mobile** to ensure responsive design works
- **Use DevTools** (F12) to debug issues

With this guide, you should be able to confidently maintain and customize this landing page for your needs. Start with small changes and test thoroughly before making larger modifications.