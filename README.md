## Q1. What is CSS and how do you add it to an HTML page?
### Theory
* **What CSS stands for:** CSS stands for **Cascading Style Sheets**.
* **What problem does it solve:** In early HTML, styling a website required changing the fonts and colors of every single page manually. If a website had 50 pages, it was very messy and time-consuming. CSS solves this problem by separating the design/presentation from the HTML structure, allowing us to change the entire website's look from one single place.
* **Three methods of adding CSS:**
  1. **External CSS:** Writing CSS rules in a separate `.css` file and linking it in the HTML `<head>`.
  2. **Internal CSS:** Writing CSS rules inside a `<style>` tag directly inside the HTML `<head>`.
  3. **Inline CSS:** Applying styles directly to an HTML element using the `style` attribute.
* **Why external CSS is preferred over inline CSS:** External CSS keeps the HTML code clean, readable, and highly reusable. Instead of repeating styling code on every HTML element (like inline CSS), external CSS allows you to manage and update the design of an entire multi-page website by editing just one stylesheet.
### Code Task: Methods of Adding CSS
#### 1. External CSS (Recommended Method)
First, we create a file named `style.css`:
```css
/* style.css */
p {
    color: green;
    font-size: 18px;
}
<head>
    <link rel="stylesheet" href="style.css">
</head>
<head>
    <style>
        h1 {
            color: blue;
            text-align: center;
        }
    </style>
</head>
<button style="background-color: red; color: white; padding: 10px;">
    Click Here
</button>
```
## Q2. Explain CSS Selectors with examples.
### Theory
* **What is a CSS Selector:** A CSS selector is a pattern used to target or point to the specific HTML elements you want to style. Without selectors, the browser would not know where to apply your CSS rules.

* **Detailed Concept Breakdown (Points to Cover):**
  * **Which selector has the highest specificity — class or ID?** An **ID selector** has a much higher specificity (strength) than a class selector. If there is a conflict, the ID style wins.
  * **Can you use the same class on multiple elements?** **Yes.** Classes are designed to be reusable. You can apply the same class name to as many HTML elements as you want.
  * **Can you use the same ID on multiple elements?** **No.** An ID must be completely unique on a webpage. It can only be used for one single element per page.
  * **When to use a class vs an ID:** Use a **class** when you want to apply the same styling to a group of multiple elements (like buttons or cards). Use an **ID** only when targeting a single, unique element that needs special styling (like a main navigation bar or header).
  * **How do you target an element that is a direct child vs any descendant?** * To target a **direct child**, we use the `>` combinator (e.g., `div > p` only styles paragraphs directly inside that div).
    * To target **any descendant** (anywhere inside, even nested deeply), we use a simple space (e.g., `div p` styles every single paragraph inside that div, no matter how deep).
### Code Task: Examples of All 7 Selector Types
#### 1. Element Selector (Targets all tags of this type)
```css
p {
    color: darkblue;
}
<div class="card">Box 1</div>
.card {
    background-color: lightgray;
    padding: 10px;
}
<h1 id="main-title">Welcome</h1>
#main-title {
    text-align: center;
}
h1, h2, h3 {
    font-family: Arial, sans-serif;
    color: green; /* Applies to all three headings at once */
}
<div class="box">
    <span>Inside Box</span>
</div>
.box span {
    font-weight: bold; /* Styles any span inside .box */
}
<ul class="parent-list">
    <li>Direct Child</li>
</ul>
.parent-list > li {
    list-style-type: square; /* Only targets li directly inside .parent-list */
}
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```
## Q3. What is the CSS Box Model? Explain each layer.
### Theory
* **What is the CSS Box Model:** In CSS, every HTML element is treated as a rectangular box. The Box Model is a set of rules that decides the total size (width and height) of that box on a webpage.
* **The 4 Layers of Box Model:**
  1. **Content:** This is the actual text, image, or video. It is the **innermost** layer.
  2. **Padding:** This is the clearing area/space around the content. It sits **inside** the border to give the text breathing room.
  3. **Border:** This is a boundary line that wraps around both the padding and content.
  4. **Margin:** This is the outermost space **outside** the border. It separates this box from other elements.
### Detailed Concept Breakdown (Assignment Questions)
* **Which layer is the innermost?** The **Content** layer is the innermost layer of the box model.
* **Padding is inside or outside the border?** Padding is strictly **inside** the border.
* **What does `margin: 0 auto;` do to a block element?** It centers a block element horizontally inside its parent container. `0` resets the top and bottom margins, while `auto` tells the browser to apply equal space on both the left and right sides automatically.
* **With `border-box`, does width include padding?** Yes! When using `box-sizing: border-box;`, the defined width **includes** both the padding and the border. The box will not grow larger than your specified width.

* **Difference between content-box and border-box:**
  * **content-box (Default):** Padding and borders are added *outside* the width. If width is 300px, adding 20px padding makes the actual box 340px wide, which often breaks grid layouts.
  * **border-box (Used in Professional Projects):** Padding and borders are absorbed *inside* the width. The visible box stays exactly 300px. Professional projects always use `border-box` because it makes sizing completely predictable.
### Code Task: Box Model CSS Rule
```css
.box {
    box-sizing: border-box; /* Width includes padding and border */
    width: 300px;           /* Exact total layout width */
    padding: 20px;          /* Inside clearing space */
    border: 2px solid;      /* Boundary lines */
    margin: 16px;           /* Outside spacing from other items */
}
```
## Q4. Explain CSS Colors. What are the different ways to define a color?
### Theory
* **What are CSS Colors:** Colors in CSS are used to style text, backgrounds, borders, and other design elements. There are multiple formats to define colors depending on the level of control and transparency required.
* **The 5 Color Formats:**
  1. **Named Colors:** Standard color names recognized by browsers (e.g., `red`, `blue`, `orange`).
  2. **HEX (Hexadecimal):** A 6-character code starting with a hash (`#`) representing Red, Green, and Blue values in hex digits (e.g., `#F97316`).
  3. **RGB:** Defines color using three numbers from 0 to 255 for Red, Green, and Blue (e.g., `rgb(249, 115, 22)`).
  4. **RGBA:** Same as RGB, but adds a fourth value called Alpha (from 0.0 to 1.0) to control transparency/opacity.
  5. **HSL:** Defines color using Hue (0-360 degrees on color wheel), Saturation (percentage), and Lightness (percentage).
### Detailed Concept Breakdown (Assignment Questions)
* **Which format is most commonly used by developers?** **HEX codes** are the most commonly used by developers because they are short, precise, and easily copied from design tools like Figma. However, **RGBA** is heavily used when transparency is needed.
* **What does the 'A' in RGBA stand for?** The 'A' stands for **Alpha**, which controls the transparency or opacity of the color.
* **Does opacity affect child elements?** **Yes.** When you use `opacity: 0.5;` on a parent element, the entire element **including all its text, buttons, and child elements** becomes 50% transparent.
* **Does rgba affect child elements?** **No.** When you use `rgba(0,0,0,0.5)` as a background color, it **only** makes the background transparent. The text and child elements inside it remain completely solid (100% visible).
### Code Task: Orange Color (`#F97316`) in All 5 Formats
Here is how you write the exact same orange color using all five methods required by the assignment:
```css
/* 1. Named Color Format */
.orange-box {
    color: orange; 
}

/* 2. HEX Format (Given in assignment) */
.orange-box {
    color: #F97316; 
}

/* 3. RGB Format */
.orange-box {
    color: rgb(249, 115, 22); 
}

/* 4. RGBA Format (1.0 means fully solid/opaque) */
.orange-box {
    color: rgba(249, 115, 22, 1.0); 
}

/* 5. HSL Format */
.orange-box {
    color: hsl(25, 95%, 53%); 
}
```
## Q5. What are CSS Units? Explain px, %, rem, em, vh, and vw.
### Theory & Golden Rules
* **What are CSS Units:** CSS units are measurements used to define the size of text, padding, margins, widths, heights, and other spacing elements on a web page.
* **The Golden Rules for Layouts:**
  1. **For Font Sizes:** Always prefer **rem** units to make text accessible and scalable.
  2. **For Widths:** Prefer **percentages (%)** or **rem/em** to keep boxes responsive.
  3. **For Full-Screen Sections:** Always use **vh (Viewport Height)** and **vw (Viewport Width)**.
### Detailed Concept Breakdown (Assignment Questions)
* **What is 1rem equal to by default?** By default, `1rem` is equal to **16px** (which is the standard root font-size of almost all modern web browsers).
* **Is % relative to the parent or the root?** A percentage (`%`) unit is strictly relative to its immediate **parent element**, not the root.
* **What does vh stand for?** `vh` stands for **Viewport Height**. `1vh` is equal to 1% of the browser window's total height.
* **Why is rem better than px for font-size in accessibility?** If a user changes their browser's default text size (for example, visually impaired users making text larger), text defined in `px` remains frozen and does not grow. However, text defined in `rem` scales beautifully according to the user's custom settings, making the website fully accessible.
### Sizing Units Guide Table

| Unit | What it is Relative To | Practical Use Case | Example |
| :--- | :--- | :--- | :--- |
| **px** | Absolute pixels (fixed size) | Small, fixed borders or shadows | `border: 2px solid;` |
| **%** | Relative to the Parent element's size | Responsive layout columns and grids | `width: 50%;` |
| **rem** | Relative to the Root element (`<html>`) | Font sizes, padding, and margins | `font-size: 1.2rem;` |
| **em** | Relative to the element's own font-size | Padding inside buttons that scales with text | `padding: 0.5em;` |
| **vh** | Relative to 1% of Viewport (Screen) Height | Creating a full-screen landing section | `height: 100vh;` |
| **vw** | Relative to 1% of Viewport (Screen) Width | Text or hero sections that scale with screen width | `width: 100vw;` |
### Code Task: Responsive Hero Section
Here is the perfect CSS rule for a full-screen hero section using fluid fonts and accessible sizing:

```css
.hero-section {
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    
    /* 1. Full viewport height */
    width: 100vw;
    height: 100vh; 
    
    /* 2. Max-width uses rem for crisp layout control */
    max-width: 75rem; /* 75rem * 16px = 1200px max width container */
    margin: 0 auto;   /* Centers the block container horizontally */
    
    padding: 2rem;
    background-color: #f4f4f4;
}

.hero-section h1 {
    /* 3. Font-size scales dynamically with viewport width */
    font-size: 5vw; 
    min-font-size: 2rem; /* Fallback protection for small screens */
    color: #333;
}
```
## Q6. What is CSS Specificity and how does the Cascade work?
### Theory
* **How the Cascade works:** "Cascading" means that the browser reads and applies CSS rules from top to bottom (Source Order). It also considers Specificity (strength) and Inheritance (properties passed from parent to child).
* **What is CSS Specificity:** Specificity is the scoring system or weight that browsers use to determine which CSS rule wins when multiple selectors target the exact same element.
* **What `!important` does and why it should be avoided:** The `!important` rule overrides all other specificity levels completely, forcing that style to win. It should be avoided because it breaks the natural cascade, making the CSS chaotic and extremely difficult to debug or override later.
### Detailed Concept Breakdown (Assignment Questions)
* **Which higher specificity — a class or an element selector?** A **class selector** has a higher specificity than a standard element selector.
* **What specificity score does an inline style have?** Inline styles have the highest weight in a standard CSS sheet, often represented as a score of **(1, 0, 0, 0)** or **1000** compared to IDs (100) and classes (10).
* **If two rules have equal specificity, which one wins?** If the specificity is exactly equal, the **Cascade** rule takes over, meaning the rule written **last (at the bottom of the file)** wins.
* **What does `!important` override?** It overrides everything: element selectors, classes, IDs, and inline styles.
### Code Task: Specificity Conflict Example
Given HTML: `<p id="intro" class="text">Hello</p>`
```css
/* 1. Element Selector (Weakest - Score: 0,0,0,1) */
p {
    color: red;
}

/* 2. Class Selector (Medium - Score: 0,0,1,0) */
.text {
    color: blue;
}

/* 3. ID Selector (Strongest - Score: 0,1,0,0) - THIS WINS! */
#intro {
    color: green; /* The text "Hello" will be GREEN */
}
```
## Q7. Explain CSS Flexbox. How does it differ from block layout?
### Theory
* **What is Flexbox:** Flexbox (Flexible Box Layout) is a 1-dimensional layout system designed for aligning elements in either a row or a column.
* **How it differs from standard block layout:** Standard block layout stacks elements vertically on top of each other by default and lacks easy alignment tools. Flexbox, once activated with `display: flex;`, allows items to automatically shrink, grow, stretch, and align beautifully along axes without calculating fixed dimensions.
* **Two Real-World Use Cases for Flexbox:**
  1. Creating a responsive Navigation Bar (Logo on left, links on right).
  2. Perfectly centering a login form or modal card horizontally and vertically inside a screen.

### Detailed Concept Breakdown (Assignment Questions)
* **What is the difference between justify-content and align-items?**
  * `justify-content` aligns items along the **Main Axis** (horizontally by default in a row).
  * `align-items` aligns items along the **Cross Axis** (vertically by default in a row).
* **What does `flex: 1;` do to an item?** It tells the flex item to grow and shrink dynamically so that it fills up all the available remaining empty space inside the parent container.
* **How do you center an element both horizontally and vertically with Flexbox?** You apply these three magic lines to the parent container:
  ```css
  display: flex;
  justify-content: center; /* Centers horizontally */
  align-items: center;     /* Centers vertically */
**What does flex-wrap:** Wrap; do? By default, flex items try to fit on one single line. flex-wrap: wrap; allows items to automatically drop down onto a new row if there isn't enough screen width.
## Code Task: Responsive Flexbox Navbar
Here is the professional CSS rule for a clean navigation bar according to the criteria:
<nav class="navbar">
    <div class="logo">MyLogo</div>
    <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</nav>
/* CSS Rules */
.navbar {
    display: flex;
    justify-content: space-between; /* Logo on left, links on right */
    align-items: center;            /* Perfectly centers items vertically */
    padding: 1rem 2rem;
    background-color: #ffffff;
}

.nav-links {
    display: flex;
    gap: 1.5rem;                   /* Creates an equal gap between links */
    list-style: none;
    margin: 0;
    padding: 0;
}

.nav-links a {
    text-decoration: none;
    color: #333;
}
---
## Q8. What are CSS Pseudo-classes and Pseudo-elements?
### Theory
* **What is a Pseudo-class:** A pseudo-class is used to define a special **state** of an element (e.g., when a user hovers over a button, or when an input field gets focus). It uses a single colon (`:`).
* **What is a Pseudo-element:** A pseudo-element is used to style a specific **part** of an element, or inject virtual content before/after it. It uses a double colon (`::`).
* **The `content` property:** The `content` property is required when using `::before` or `::after`. Without it, the pseudo-element will not appear on the page at all, even if you set a width and height.

### Detailed Concept Breakdown (Assignment Questions)
* **Does `::before` add a real HTML element?** **No.** It adds a "virtual" or pseudo-element that appears inside the browser window, but it does not alter or add any new tag to the actual HTML source code.
* **What CSS property is required for `::before`/`::after` to appear?** The **`content: "";`** property is strictly required.
* **What elements does `:nth-child(2n)` select?** It selects all **even-numbered** child elements (e.g., the 2nd, 4th, 6th, 8th items in a list).
* **How would you style every 3rd list item?** You would use the **`:nth-child(3n)`** pseudo-class selector.
### Code Task: Interactive Elements & Placeholders
Here is the perfect CSS according to Sir's requirements (Orange hover button, star icon before featured items, and grey placeholder text):
```css
/* 1. Turns a button orange on hover */
button:hover {
    background-color: #F97316; /* Orange color */
    color: white;
}

/* 2. Adds a star (★) before every .featured list item */
.featured::before {
    content: "★ "; /* Required property to show virtual content */
    color: gold;
    font-weight: bold;
}

/* 3. Styles placeholder text grey in an input */
input::placeholder {
    color: #888888; /* Soft grey color */
    font-style: italic;
}
```
## Q9. Explain CSS Transitions and Animations.
### Theory
* **Difference between Transitions and Animations:** * **Transitions:** Move an element smoothly from state A to state B when triggered by a user action (like hovering over a button). It needs an explicit trigger.
  * **Animations:** Are more complex, can have multiple keyframes/stages, and can run automatically when the page loads without needing any user interaction.
* **The `@keyframes` rule:** It is used to define the stages and styles of a CSS animation from start (`0%`) to finish (`100%`).
* **Why prefer `transform` and `opacity` for animations:** Changing properties like `width`, `height`, or `margin` forces the browser to recalculate the layout of the entire page (Reflow), which makes animations laggy. `transform` (like `translateY`) and `opacity` are handled directly by the GPU, ensuring buttery-smooth 60fps performance.

### Detailed Concept Breakdown (Assignment Questions)
* **What are common triggers for a transition?** Common triggers are user interactions via pseudo-classes like `:hover`, `:focus`, `:active`, or adding/removing a class via JavaScript.
* **Can you have multiple transitions on one element?** **Yes.** You can transition multiple properties at once by separating them with commas (e.g., `transition: background-color 0.3s, transform 0.5s;`).
* **What does `animation-iteration-count: infinite;` do?** It makes the animation loop forever without stopping.
* **What does `animation-fill-mode: forwards;` do?** It tells the browser to keep the final styles applied by the last keyframe (`100%`) after the animation finishes, instead of snapping back to the original styles.
### Code Task: Interactive Card and Page-Load Fade Animation
```css
/* 1. Keyframe for Page-Load Fade-In and Slide-Up Animation */
@keyframes fadeInUp {
    0% {
        opacity: 0;
        transform: translateY(20px); /* Starts lower and invisible */
    }
    100% {
        opacity: 1;
        transform: translateY(0);    /* Moves to normal position */
    }
}

/* 2. Applying Animation to the Card on Page Load */
.card {
    width: 300px;
    padding: 20px;
    background: white;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    
    /* Animation setup */
    animation: fadeInUp 0.8s ease-out;
    animation-fill-mode: forwards; /* Holds the 100% state */
    
    /* Smooth transition setup for hover interactions */
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

/* 3. Card Hover Effect (Smoothly lifts up and adds deep shadow) */
.card:hover {
    transform: translateY(-10px); /* Lift up effect */
    box-shadow: 0 12px 20px rgba(0, 0, 0, 0.15); /* Shadow expands */
}
```
## Q10. What is Responsive Web Design? Explain Media Queries, CSS Variables, and Mobile-First approach.
### Theory & Explanations
* **What is Responsive Web Design (RWD):** It is a practice of creating web pages that look great and function perfectly on all devices (Desktops, laptops, tablets, and phones) by dynamically adapting to different screen sizes.
* **Part A — Media Queries:** Media queries allow you to apply specific CSS rules only if certain conditions are met, such as a device screen being wider or narrower than a specific size.
* **Part B — Mobile-First Approach:** This means writing the core CSS code for small screen sizes (mobiles) first without media queries, and then using `min-width` media queries to add complex layers of layout structures as the screen gets wider. This is the industry standard because mobile devices have less hardware power, so loading cleaner CSS initially is highly efficient.
* **Part C — CSS Variables:** Also known as Custom Properties, they allow you to store specific values (like a hex code or font-size) in one place and reuse them throughout your stylesheet.
### Detailed Concept Breakdown (Assignment Questions)
* **In mobile-first, do you use min-width or max-width in media queries?** You strictly use **`min-width`** because you start small and scale up.
* **What does `@media (prefers-color-scheme: dark)` do?** It checks if the user has enabled "Dark Mode" in their operating system or device settings and automatically applies dark styles if true.
* **Can JavaScript read and change CSS variables?** **Yes.** JavaScript can access them using `getPropertyValue()` and alter them dynamically using `style.setProperty()`, which is great for user-controlled theme switchers.
* **What is the difference between `var(--color)` and `var(--color, fallback)`?** `var(--color)` will fail if the variable isn't defined. `var(--color, fallback)` provides a secondary backup color (`fallback`) that the browser can display if the main custom property is missing or fails.
### Code Task: Root Variables System with Responsive Breakdown & Dark Theme
```css
/* Defining Global Design System in :root */
:root {
    --primary-color: #3b82f6;      /* Vibrant Blue */
    --background-color: #ffffff;   /* Pure White */
    --text-color: #1f2937;         /* Dark Grey */
    --font-base: 1rem;
    --spacing-md: 1.5rem;
}

/* Automatic Dark Mode Implementation */
@media (prefers-color-scheme: dark) {
    :root {
        --background-color: #111827; /* Dark Charcoal */
        --text-color: #f9fafb;       /* Soft Off-White */
    }
}

/* Explicit Data-Attribute Override (for manual toggle buttons) */
[data-theme="dark"] {
    --background-color: #111827;
    --text-color: #f9fafb;
}

/* Base Mobile Layout (Applied by default) */
body {
    background-color: var(--background-color);
    color: var(--text-color);
    font-size: var(--font-base);
    padding: var(--spacing-md);
    transition: background-color 0.3s ease, color 0.3s ease;
}

.container {
    display: flex;
    flex-direction: column; /* Stack vertically on mobile devices */
    gap: 1rem;
}

/* Tablet Media Query (768px and up) */
@media (min-width: 768px) {
    :root {
        --font-base: 1.1rem; /* Slightly larger typography */
    }
    .container {
        flex-direction: row; /* Switch to side-by-side row columns */
    }
}

/* Desktop Media Query (1024px and up) */
@media (min-width: 1024px) {
    :root {
        --font-base: 1.2rem;
        --spacing-md: 2.5rem; /* Expanded breathing space */
    }
    .container {
        max-width: 1200px;
        margin: 0 auto;
    }
}