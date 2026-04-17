# InCheck Solutions Design System

Reference document for replicating InCheck's design at scale for landing pages.

**Website:** https://www.inchecksolutions.com/
**Industry:** Background Screening / HR Tech

---

## Color Palette

### Primary Brand Colors

| Color Name | Hex Value | Usage |
|------------|-----------|-------|
| Primary Orange | `#f05e24` | CTAs, buttons, hover states, accent borders |
| Teal/Turquoise | `#61c3b5` | Secondary accent, feature highlights, top borders |
| Gold/Yellow | `#f8ae2c` | Tertiary accent, highlights |

### Neutral Colors

| Color Name | Hex Value | Usage |
|------------|-----------|-------|
| Dark Gray | `#828282` | Primary body text |
| Medium Gray | `#707070` | Headings, secondary text |
| Light Gray | `#f2f2f2` | Page background |
| Off-White | `#fbfbfb` | Card hover background |
| White | `#ffffff` | Cards, content backgrounds |
| Black | `#000000` | Strong text, borders |

### Semantic Colors

| Color Name | Hex Value | Usage |
|------------|-----------|-------|
| Error | `#dd6420` | Error states, validation |
| Link Blue | `#1863dc` | Cookie consent links (secondary) |
| Light Blue | `#78ccea` | Accent section backgrounds |

### CSS Variables (Tailwind Equivalents)

```css
/* Custom CSS */
:root {
  --incheck-orange: #f05e24;
  --incheck-teal: #61c3b5;
  --incheck-yellow: #f8ae2c;
  --incheck-gray-dark: #828282;
  --incheck-gray-medium: #707070;
  --incheck-gray-light: #f2f2f2;
  --incheck-white: #ffffff;
  --incheck-black: #000000;
}
```

```js
// Tailwind config extension
colors: {
  incheck: {
    orange: '#f05e24',
    teal: '#61c3b5',
    yellow: '#f8ae2c',
    'gray-dark': '#828282',
    'gray-medium': '#707070',
    'gray-light': '#f2f2f2',
    'light-blue': '#78ccea',
  }
}
```

---

## Typography

### Font Family

**Primary Font:** Montserrat (Google Fonts)

```html
<!-- CDN Link -->
<link href="https://fonts.googleapis.com/css?family=Montserrat:300,400,600,700&display=swap" rel="stylesheet">
```

```css
/* CSS */
font-family: 'Montserrat', sans-serif;
```

```js
// Tailwind config
fontFamily: {
  sans: ['Montserrat', 'sans-serif'],
}
```

### Font Weights

| Weight | Value | Usage |
|--------|-------|-------|
| Light | 300 | Subtle text |
| Regular | 400 | Body text |
| Semi-Bold | 600 | Subheadings, buttons |
| Bold | 700 | Headings, emphasis |

### Font Sizes

| Element | Size | Line Height | Tailwind |
|---------|------|-------------|----------|
| H1 | 45px | 1.15 | `text-[45px] leading-[1.15]` |
| H2 | 30px | 1.3 | `text-[30px] leading-[1.3]` |
| H3 | 24px | 1.4 | `text-2xl leading-relaxed` |
| H4 | 20px | 1.4 | `text-xl leading-relaxed` |
| Body | 16px | 1.6 | `text-base leading-relaxed` |
| Small | 14px | 1.5 | `text-sm leading-normal` |
| XS | 13px | 1.5 | `text-[13px]` |

### Heading Styles

```html
<!-- H1 -->
<h1 class="text-[45px] font-bold text-[#707070] uppercase tracking-wide leading-[1.15]">
  Heading One
</h1>

<!-- H2 -->
<h2 class="text-[30px] font-bold text-[#828282] leading-[1.3]">
  Heading Two
</h2>

<!-- H3 -->
<h3 class="text-xl font-semibold text-[#707070]">
  Heading Three
</h3>
```

---

## Visual Elements

### Border Radius

| Size | Value | Tailwind | Usage |
|------|-------|----------|-------|
| None | 0 | `rounded-none` | Some inputs |
| Small | 2px | `rounded-sm` | Subtle rounding |
| Default | 4px | `rounded` | Cards, containers |
| Medium | 6px | `rounded-md` | Modals |
| Large | 50px | `rounded-[50px]` | Some buttons |
| Full | 9999px | `rounded-full` | Pills, primary buttons |

### Box Shadows

```css
/* Card Shadow */
box-shadow: 7px 7px 7px 0 rgba(0, 0, 0, 0.15);

/* Subtle Shadow */
box-shadow: 5px 5px 25px 2px rgba(130, 130, 130, 0.25);

/* Navigation/Header Shadow */
box-shadow: 0 1px 20px rgba(0, 0, 0, 0.1);

/* Light Shadow */
box-shadow: 0 0 7px rgba(0, 0, 0, 0.1);

/* Modal Shadow */
box-shadow: 0 32px 68px rgba(0, 0, 0, 0.3);

/* Input Focus */
box-shadow: 0 1px 4px 1px rgba(0, 0, 0, 0.1);
```

```js
// Tailwind config
boxShadow: {
  'incheck-card': '7px 7px 7px 0 rgba(0, 0, 0, 0.15)',
  'incheck-subtle': '5px 5px 25px 2px rgba(130, 130, 130, 0.25)',
  'incheck-nav': '0 1px 20px rgba(0, 0, 0, 0.1)',
  'incheck-light': '0 0 7px rgba(0, 0, 0, 0.1)',
  'incheck-modal': '0 32px 68px rgba(0, 0, 0, 0.3)',
}
```

### Border Styles

```css
/* Accent Top Border (Feature Cards) */
border-top: 5px solid #61c3b5;

/* Standard Border */
border: 1px solid #949494;

/* CTA Link Bottom Border */
border-bottom: 2px solid #f05e24;
```

---

## Component Patterns

### Primary Button (Pill Style)

```html
<button class="
  bg-[#f05e24]
  text-white
  font-semibold
  uppercase
  px-6 py-3
  rounded-full
  border-2 border-[#f05e24]
  hover:bg-white
  hover:text-[#f05e24]
  transition-all duration-300
">
  Get Started
</button>
```

```css
/* CSS Version */
.btn-primary {
  background-color: #f05e24;
  color: #fff;
  font-weight: 600;
  text-transform: uppercase;
  padding: 12px 24px;
  border-radius: 9999px;
  border: 2px solid #f05e24;
  transition: all 0.3s ease;
}

.btn-primary:hover {
  background-color: #fff;
  color: #f05e24;
}
```

### Secondary Button (Outline)

```html
<button class="
  bg-white
  text-[#f05e24]
  font-semibold
  uppercase
  px-6 py-3
  rounded-full
  border-2 border-[#f05e24]
  hover:bg-[#f05e24]
  hover:text-white
  transition-all duration-300
">
  Learn More
</button>
```

### Service Card

```html
<div class="
  bg-white
  rounded
  p-5
  text-center
  shadow-[7px_7px_7px_0_rgba(0,0,0,0.15)]
  border-t-[5px] border-[#61c3b5]
  hover:bg-[#fbfbfb]
  transition-all duration-300
">
  <img src="icon.png" class="w-[120px] mx-auto mb-4" alt="">
  <h3 class="text-xl font-bold text-[#707070] mb-2 hover:text-[#f05e24] transition-colors">
    Service Title
  </h3>
  <p class="text-[#828282] text-[15px]">
    Service description text goes here.
  </p>
</div>
```

### Feature Card (with Teal Top Border)

```html
<div class="
  bg-white
  border-t-[5px] border-[#61c3b5]
  shadow-[7px_7px_7px_0_rgba(0,0,0,0.15)]
  p-6
  rounded
">
  <h3 class="text-xl font-semibold text-[#707070] mb-3">
    Feature Title
  </h3>
  <p class="text-[#828282]">
    Feature description goes here with supporting details.
  </p>
</div>
```

### CTA Link

```html
<a href="#" class="
  text-[#f05e24]
  font-semibold
  uppercase
  text-sm
  border-b-2 border-[#f05e24]
  hover:opacity-80
  transition-opacity
">
  Learn More <span class="ml-1">&rarr;</span>
</a>
```

---

## Form Styles

### Input Fields

```html
<input type="text" class="
  w-full
  px-4 py-3
  border border-[#949494]
  rounded
  text-[#828282]
  focus:border-[#f05e24]
  focus:bg-[#fcfcfc]
  focus:shadow-[0_1px_4px_1px_rgba(0,0,0,0.1)]
  focus:outline-none
  transition-all
" placeholder="Enter text...">
```

```css
/* CSS Version */
input, textarea {
  padding: calc(0.667em + 2px);
  border: 1px solid #949494;
  border-radius: 4px;
  font-size: 1em;
  font-family: inherit;
}

input:focus, textarea:focus {
  border-color: #f05e24;
  background-color: #fcfcfc;
  box-shadow: 0 1px 4px 1px rgba(0, 0, 0, 0.1);
  outline: none;
}
```

### Form Submit Button

```html
<button type="submit" class="
  bg-[#f05e24]
  text-white
  font-semibold
  px-6 py-3
  rounded-full
  border-2 border-[#f05e24]
  hover:bg-white
  hover:text-[#f05e24]
  transition-all duration-300
  w-full md:w-auto
">
  Submit
</button>
```

### Error States

```css
/* Error Input */
input.error {
  border-color: #dd6420;
}

/* Error Message */
.error-message {
  color: #dd6420;
  font-size: 12px;
  padding-top: 8px;
}
```

---

## Layout Patterns

### Header/Navigation

```html
<header class="
  bg-white/90
  backdrop-blur-sm
  shadow-[0_1px_20px_rgba(0,0,0,0.1)]
  sticky top-0 z-50
">
  <div class="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between">
    <img src="logo.png" alt="InCheck" class="h-8">
    <nav class="hidden md:flex items-center space-x-8">
      <a href="#" class="text-[#828282] font-semibold hover:text-[#f05e24] transition-colors">
        Services
      </a>
      <!-- More nav items -->
    </nav>
    <button class="
      bg-[#f05e24] text-white font-semibold
      px-4 py-2 rounded-full text-sm
      hover:bg-white hover:text-[#f05e24]
      border-2 border-[#f05e24]
      transition-all
    ">
      Contact Us
    </button>
  </div>
</header>
```

### Hero Section

```html
<section class="bg-white py-16 md:py-24">
  <div class="max-w-6xl mx-auto px-4 text-center">
    <h1 class="
      text-[45px] font-bold text-[#707070]
      uppercase tracking-wide leading-[1.15]
      mb-6
    ">
      Main Headline Here
    </h1>
    <p class="text-[#828282] text-lg max-w-2xl mx-auto mb-8">
      Supporting description text that explains the value proposition.
    </p>
    <div class="flex flex-col sm:flex-row gap-4 justify-center">
      <button class="
        bg-[#f05e24] text-white font-semibold uppercase
        px-8 py-4 rounded-full border-2 border-[#f05e24]
        hover:bg-white hover:text-[#f05e24]
        transition-all
      ">
        Primary CTA
      </button>
      <button class="
        bg-white text-[#f05e24] font-semibold uppercase
        px-8 py-4 rounded-full border-2 border-[#f05e24]
        hover:bg-[#f05e24] hover:text-white
        transition-all
      ">
        Secondary CTA
      </button>
    </div>
  </div>
</section>
```

### Services Grid

```html
<section class="bg-[#f2f2f2] py-16">
  <div class="max-w-6xl mx-auto px-4">
    <h2 class="text-[30px] font-bold text-[#828282] text-center mb-12">
      Our Services
    </h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <!-- Service Card -->
      <div class="
        bg-white p-6 rounded text-center
        border-t-[5px] border-[#61c3b5]
        shadow-[7px_7px_7px_0_rgba(0,0,0,0.15)]
        hover:bg-[#fbfbfb]
        transition-all
      ">
        <img src="icon.png" class="w-24 mx-auto mb-4" alt="">
        <h3 class="text-xl font-bold text-[#707070] mb-3">
          Service Name
        </h3>
        <p class="text-[#828282] text-[15px] mb-4">
          Brief description of this service offering.
        </p>
        <a href="#" class="
          text-[#f05e24] font-semibold uppercase text-sm
          border-b-2 border-[#f05e24]
          hover:opacity-80
        ">
          Learn More
        </a>
      </div>
      <!-- Repeat for more cards -->
    </div>
  </div>
</section>
```

### CTA Section

```html
<section class="bg-[#78ccea] py-16">
  <div class="max-w-4xl mx-auto px-4 text-center">
    <h2 class="text-[30px] font-bold text-white mb-4">
      Ready to Get Started?
    </h2>
    <p class="text-white/90 text-lg mb-8">
      Contact us today to learn how we can help streamline your background screening.
    </p>
    <button class="
      bg-white text-[#78ccea] font-semibold uppercase
      px-8 py-4 rounded-full border-2 border-white
      hover:bg-transparent hover:text-white
      transition-all
    ">
      Contact Us
    </button>
  </div>
</section>
```

### Footer

```html
<footer class="bg-[#1a1a1a] text-white py-12">
  <div class="max-w-6xl mx-auto px-4">
    <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-8">
      <div>
        <img src="logo-white.png" alt="InCheck" class="h-8 mb-4">
        <p class="text-gray-400 text-sm">
          Background screening solutions for modern businesses.
        </p>
      </div>
      <div>
        <h4 class="font-bold text-[#f05e24] mb-4">Services</h4>
        <ul class="space-y-2">
          <li><a href="#" class="text-gray-400 hover:text-white transition-colors">Background Checks</a></li>
          <!-- More links -->
        </ul>
      </div>
      <!-- More columns -->
    </div>
    <div class="border-t border-gray-700 pt-8 text-center text-gray-400 text-sm">
      &copy; 2026 InCheck. All rights reserved.
    </div>
  </div>
</footer>
```

---

## Spacing System

### Padding Scale

| Name | Value | Tailwind |
|------|-------|----------|
| xs | 5px | `p-1` |
| sm | 10px | `p-2.5` |
| md | 15px | `p-4` |
| lg | 20px | `p-5` |
| xl | 35px | `p-9` |
| 2xl | 50px | `p-12` |

### Common Spacing Patterns

```css
/* Module Margins */
margin: 20px;

/* Row Padding */
padding: 20px 0;

/* Section Padding */
padding: 35px 0;
padding: 50px 0;

/* Container Max Width */
max-width: 1112px;
max-width: 1132px;
```

---

## Icons

**Style:** Font Awesome 5

```html
<!-- CDN (if needed) -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
```

**Icon Sizing:**
- Standard: 16px-20px
- Feature Icons: 24px
- Large Icons: 120px (images)

**Icon Colors:**
- Primary: `#f05e24`
- Secondary: `#61c3b5`
- Neutral: `#828282`

---

## Animations & Transitions

```css
/* Standard Transition */
transition: all 0.3s ease;
transition: all 0.3s linear;

/* Color Transition */
transition: color 0.3s ease;

/* Background Transition */
transition: background-color 0.3s ease;
```

```js
// Tailwind config
transitionDuration: {
  DEFAULT: '300ms',
}
```

---

## Complete Tailwind Config

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        incheck: {
          orange: '#f05e24',
          teal: '#61c3b5',
          yellow: '#f8ae2c',
          'gray-dark': '#828282',
          'gray-medium': '#707070',
          'gray-light': '#f2f2f2',
          'light-blue': '#78ccea',
          error: '#dd6420',
        }
      },
      fontFamily: {
        sans: ['Montserrat', 'sans-serif'],
      },
      fontSize: {
        'h1': ['45px', { lineHeight: '1.15' }],
        'h2': ['30px', { lineHeight: '1.3' }],
        'h3': ['24px', { lineHeight: '1.4' }],
        'h4': ['20px', { lineHeight: '1.4' }],
      },
      boxShadow: {
        'incheck-card': '7px 7px 7px 0 rgba(0, 0, 0, 0.15)',
        'incheck-subtle': '5px 5px 25px 2px rgba(130, 130, 130, 0.25)',
        'incheck-nav': '0 1px 20px rgba(0, 0, 0, 0.1)',
        'incheck-light': '0 0 7px rgba(0, 0, 0, 0.1)',
        'incheck-modal': '0 32px 68px rgba(0, 0, 0, 0.3)',
        'incheck-input': '0 1px 4px 1px rgba(0, 0, 0, 0.1)',
      },
      borderRadius: {
        'pill': '9999px',
        'button': '50px',
      },
    },
  },
}
```

---

## Brand Assets

### Logo

The InCheck logo features orange and teal elements with "InCheck" text. Access via their website or request directly.

### Favicon

Available at: `https://www.inchecksolutions.com/favicon.ico`

---

## Quick Reference: Key Differentiators

1. **Orange Accent (#f05e24)** - Primary CTA color, hover states
2. **Teal Top Borders (#61c3b5)** - Feature card accent (5px top border)
3. **Pill Buttons** - Full rounded corners (9999px)
4. **Offset Shadows** - 7px 7px card shadows
5. **Montserrat Font** - Clean, modern sans-serif
6. **Uppercase Headers** - H1 often uppercase with wide tracking
7. **Gray Text Palette** - #707070 and #828282 for text hierarchy
8. **Light Gray Background** - #f2f2f2 for section contrast

---

## Sample Landing Page Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>InCheck Landing Page</title>
  <link href="https://fonts.googleapis.com/css?family=Montserrat:300,400,600,700&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: { sans: ['Montserrat', 'sans-serif'] },
          colors: {
            incheck: {
              orange: '#f05e24',
              teal: '#61c3b5',
              'gray-dark': '#828282',
              'gray-medium': '#707070',
              'gray-light': '#f2f2f2',
            }
          }
        }
      }
    }
  </script>
</head>
<body class="bg-[#f2f2f2] font-sans">

  <!-- Header -->
  <header class="bg-white/90 shadow-[0_1px_20px_rgba(0,0,0,0.1)] sticky top-0 z-50">
    <div class="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between">
      <span class="text-xl font-bold text-[#f05e24]">InCheck</span>
      <button class="bg-[#f05e24] text-white font-semibold px-4 py-2 rounded-full text-sm border-2 border-[#f05e24] hover:bg-white hover:text-[#f05e24] transition-all">
        Contact Us
      </button>
    </div>
  </header>

  <!-- Hero -->
  <section class="bg-white py-16">
    <div class="max-w-4xl mx-auto px-4 text-center">
      <h1 class="text-[45px] font-bold text-[#707070] uppercase tracking-wide leading-[1.15] mb-6">
        Background Screening Solutions
      </h1>
      <p class="text-[#828282] text-lg mb-8">
        Comprehensive screening services to help you make informed hiring decisions.
      </p>
      <button class="bg-[#f05e24] text-white font-semibold uppercase px-8 py-4 rounded-full border-2 border-[#f05e24] hover:bg-white hover:text-[#f05e24] transition-all">
        Get Started
      </button>
    </div>
  </section>

  <!-- Features -->
  <section class="bg-[#f2f2f2] py-16">
    <div class="max-w-6xl mx-auto px-4">
      <h2 class="text-[30px] font-bold text-[#828282] text-center mb-12">
        Why Choose Us
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div class="bg-white p-6 rounded text-center border-t-[5px] border-[#61c3b5] shadow-[7px_7px_7px_0_rgba(0,0,0,0.15)]">
          <h3 class="text-xl font-bold text-[#707070] mb-3">Fast Turnaround</h3>
          <p class="text-[#828282]">Get results quickly without sacrificing accuracy.</p>
        </div>
        <div class="bg-white p-6 rounded text-center border-t-[5px] border-[#61c3b5] shadow-[7px_7px_7px_0_rgba(0,0,0,0.15)]">
          <h3 class="text-xl font-bold text-[#707070] mb-3">Compliance First</h3>
          <p class="text-[#828282]">Stay compliant with all federal and state regulations.</p>
        </div>
        <div class="bg-white p-6 rounded text-center border-t-[5px] border-[#61c3b5] shadow-[7px_7px_7px_0_rgba(0,0,0,0.15)]">
          <h3 class="text-xl font-bold text-[#707070] mb-3">Expert Support</h3>
          <p class="text-[#828282]">Dedicated team to guide you through the process.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- CTA -->
  <section class="bg-[#78ccea] py-16">
    <div class="max-w-4xl mx-auto px-4 text-center">
      <h2 class="text-[30px] font-bold text-white mb-4">Ready to Learn More?</h2>
      <p class="text-white/90 text-lg mb-8">Contact our team for a personalized consultation.</p>
      <button class="bg-white text-[#78ccea] font-semibold uppercase px-8 py-4 rounded-full border-2 border-white hover:bg-transparent hover:text-white transition-all">
        Contact Us
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-[#1a1a1a] text-gray-400 py-8">
    <div class="max-w-6xl mx-auto px-4 text-center text-sm">
      &copy; 2026 InCheck. All rights reserved.
    </div>
  </footer>

</body>
</html>
```

---

*Document generated for 42 Agency SDR Pages project*
*Last updated: April 2026*
