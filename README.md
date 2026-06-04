## Q1. What is CSS and how do you add it to an HTML page?
### Theory
1. **What CSS stands for:** CSS means **Cascading Style Sheets**.
2. **What problem does it solve:** In old HTML, if we wanted to change the color or font of 50 pages, we had to change every single page one by one. It was very messy and took a lot of time. CSS solves this problem. It separates the design from the HTML structure, so we can change the look of the whole website from just one place.
1. **Three methods of adding CSS:** 
  1. **External CSS:** We make a separate `.css` file and link it in the HTML head.
  2. **Internal CSS:** We write the CSS rules inside a `<style>` tag inside the HTML head.
  3. **Inline CSS:** We write the style directly inside the HTML tag using the `style=""` attribute.
2. **Why external CSS is preferred:** It is the best method because it keeps our HTML code clean. We don't have to repeat code, and if we want to change the style of the entire website in the future, we only need to edit one single CSS file.
### Code Task: Methods of Adding CSS
Here is how we use the three different methods:
#### 1. External CSS (Best Method)
First, we make a file named `style.css` and add our styles:
```css
/* style.css */
p {
    color: green;
    font-size: 18px;
}
```
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

## Q2. Explain CSS Selectors with examples?
### Theory
1. What is a CSS Selector: A CSS selector is like a pointer. It tells the browser which HTML element we want to style. Without selectors, CSS won't know where to apply the colors or fonts.
2. Types of Selectors: There are many types, but the 4 main basic ones are:
1. Element Selector: It selects all elements with the same tag name (like all <p> or all <h1>).
2. Id Selector: It selects a unique element using its id attribute. We use a hash (#) symbol before the ID name in CSS.
3. Class Selector: It selects elements that have a specific class attribute. We can use it on multiple elements. We use a dot (.) symbol before the class name in CSS.
4. Universal Selector: It selects every single element on the webpage. We use an asterisk (*) symbol for this.
## Q3. What is the CSS Box Model? Explain each layer.
### Theory
1. **What is the CSS Box Model:** In CSS, every HTML element is treated as a rectangular box. The Box Model is a set of rules that decides the total size (width and height) of that box on the webpage.
2. **The 4 Layers of Box Model:** From inside to outside, a box has four parts:
  1. **Content:** This is the actual text, image, or video inside the box where your data sits.
  2. **Padding:** This is the space around the content, but inside the border. It helps create breathing room for text so it doesn't touch the border.
  3. **Border:** This is a line that wraps around the padding and content. You can make it visible with different colors and thickness.
  4. **Margin:** This is the outermost space outside the border. It separates this box from other elements on the page.
### Code Task: Box Model Example
Here is a simple example showing how we apply all these layers to a `div` box:
```css
.box-example {
    width: 300px;         /* Content size */
    padding: 20px;        /* Space inside the border */
    border: 5px solid red; /* The boundary line */
    margin: 30px;         /* Space outside the box */
    background-color: lightgray;
}
```
## Q4. Explain CSS Colors. What are the different ways to define a color?
### Theory
1. **CSS Colors:** CSS allows us to change the color of text, backgrounds, borders, and other elements. 
2. **Ways to Define Colors:** In CSS, we can specify colors in 4 main ways:
  1. **Color Names:** Using standard English names like `red`, `blue`, `green`, `purple`. There are about 140 standard color names.
  2. **Hex Codes (Hexadecimal):** A 6-character code starting with a hash (`#`) symbol. It uses numbers (0-9) and letters (A-F). For example, `#000000` is black and `#FFFFFF` is white.
  3. **RGB / RGBA:** Stands for Red, Green, Blue. We give values from 0 to 255 for each color, like `rgb(255, 0, 0)` for pure red. **RGBA** has a fourth value (A for Alpha) from 0.0 to 1.0 to control transparency (how see-through the color is).
  4. **HSL / HSLA:** Stands for Hue (color wheel angle from 0-360), Saturation (percentage of gray), and Lightness (percentage of white/black). **HSLA** also includes Alpha for transparency.
### Code Task: Examples of Defining Colors
Here is how we use different color methods in CSS:
```css
.box-name {
    color: red; /* Color Name */
}

.box-hex {
    background-color: #3498db; /* Hex Code for Blue */
}

.box-rgb {
    color: rgb(46, 204, 113); /* RGB for Green */
}

.box-rgba {
    background-color: rgba(0, 0, 0, 0.5); /* Black with 50% transparency */
}

.box-hsl {
    color: hsl(200, 100%, 50%); /* HSL Light Blue */
}
```
## Q5. What are CSS Units? Explain px, %, rem, em, vh, and vw.
### Theory
1. **What are CSS Units:** CSS units are used to express the size, padding, margin, or font-size of elements. There are two types of units: **Absolute** (fixed size) and **Relative** (changes size based on the screen or parent element).
2. **Explanation of Units:**
  1. **px (Pixels):** This is an absolute unit. `1px` is like a single tiny dot on the screen. It stays the same size on every device.
  2. **% (Percentage):** A relative unit. It calculates size relative to its parent element. If a parent box is `500px` wide and the child is `50%`, the child will be `250px`.
  3. **em:** A relative unit based on the font-size of its immediate parent element. If parent font-size is `16px`, then `1em` = `16px`, and `2em` = `32px`.
  4. **rem (Root em):** A relative unit based ONLY on the font-size of the root element (usually the `<html>` tag, which defaults to `16px`). It is much easier to use than `em` because it doesn't change with parents.
  5. **vh (Viewport Height):** Relative to the total height of the browser window screen. `1vh` is equal to 1% of the screen's height. `100vh` means full screen height.
  6. **vw (Viewport Width):** Relative to the total width of the browser window screen. `1vw` is equal to 1% of the screen's width. `100vw` means full screen width.
### Code Task: Examples of CSS Units
Here is how we apply these units in CSS:
```css
.fixed-box {
    font-size: 16px;      /* Fixed text size */
    width: 200px;         /* Fixed width */
}

.responsive-box {
    width: 50%;           /* Takes half width of its parent */
    font-size: 2rem;      /* 2 times the root font size (usually 32px) */
}

.full-screen-section {
    width: 100vw;         /* Covers full width of the screen */
    height: 100vh;        /* Covers full height of the screen */
    padding: 2em;         /* Padding relative to parent text size */
}
```
## Q6. What is CSS Specificity and how does the Cascade work?
### Theory
1. **How the Cascade works:** "Cascading" means that CSS reads the code from top to bottom. If you write two different styles for the same HTML element, the style written at the bottom (last) will overwrite the one at the top. It is like the final decision.
2. **What is CSS Specificity:** Specificity is a set of rules that browsers use to decide which CSS property value is the most important and should be applied. If two styles conflict, the browser doesn't just look at which one is at the bottom, it looks at which selector is more specific (stronger).
3. **The Specificity Hierarchy (From Strongest to Weakest):**
  1. **Inline Styles:** Directly inside the HTML tag (e.g., `style="color: red;"`). This is the strongest.
  2. **ID Selectors:** Uses `#` (e.g., `#main-header`). Very strong.
  3. **Class / Pseudo-class Selectors:** Uses `.` (e.g., `.card` or `:hover`). Medium strength.
  4. **Element Selectors:** Tag names (e.g., `p`, `h1`). Weakest.
### Code Task: Examples of Cascade and Specificity
#### 1. Example of Cascade (Top to Bottom Rule)
Here, the paragraph will turn **blue** because blue is written last:
```css
p {
    color: red;
}
p {
    color: blue; /* Wins because it is at the bottom */
}
```
<p id="special-text" class="normal-text">Hello World</p>
#special-text {
    color: green; /* ID Selector (Strongest) - THIS WINS! */
}

.normal-text {
    color: blue;  /* Class Selector (Medium) */
}

p {
    color: red;   /* Element Selector (Weakest) */
}
## Q7. Explain CSS Flexbox. How does it differ from block layout?

### Theory
* **What is CSS Flexbox:** Flexbox stands for Flexible Box Layout. It is a 1-Dimensional layout system used to align and distribute items in a single row or a single column easily, even when the screen size changes.
* **Difference from Block Layout:** * In standard **Block Layout**, elements automatically stack on top of each other (one below the other). Making them sit side-by-side used to be very hard.
  * In **Flexbox Layout**, we just write `display: flex;` on the parent box, and all child items instantly arrange themselves side-by-side in a clean row. Centering items or giving space between them becomes super easy.
### Code Task: Flexbox Example
```html
<div class="flex-container">
    <div class="box">1</div>
    <div class="box">2</div>
    <div class="box">3</div>
</div>
.flex-container {
    display: flex;
    justify-content: space-around; /* Puts equal space around boxes */
    align-items: center;           /* Centers items vertically */
    background-color: lightgray;
}
.box {
    width: 80px;
    height: 80px;
    background-color: blue;
}
```
## Q8. What are CSS Pseudo-classes and Pseudo-elements?
## Theory
1. Pseudo-classes (State of an Element): A pseudo-class is used to style an element only when it enters a special state. 
For example, when a user hovers their mouse over a button, or clicks a link. It uses a single colon (:).
2. Pseudo-elements (Part of an Element): A pseudo-element is used to style a specific part of an element, rather than the whole thing.
 For example, styling just the very first letter of a paragraph, or inserting content before/after an element. It uses a double colon (::).

 /* Pseudo-class example */
button:hover {
    background-color: green; /* Changes color only when mouse moves over it */
}

/* Pseudo-element example */
p::first-letter {
    font-size: 30px;
    font-weight: bold; /* Makes only the first letter big */
}
## Q9. Explain CSS Transitions and Animations.
## Theory
1. CSS Transitions: Transitions allow you to change a property smoothly from one state to another over a given time duration. It needs a trigger, like someone hovering a mouse over an item.
2. CSS Animations: Animations are more advanced. They can change styles automatically without needing any user trigger. They use @keyframes to define different steps or changes at different percentages of time (like 0%, 50%, 100%).
/* Transition Example */
.smooth-box {
    width: 100px;
    background-color: red;
    transition: width 0.5s ease; /* Changes width smoothly in 0.5 seconds */
}
.smooth-box:hover {
    width: 200px;
}

/* Animation Example */
.moving-box {
    width: 50px;
    height: 50px;
    background-color: blue;
    animation: slide 3s infinite; /* Runs the 'slide' animation forever */
}

@keyframes slide {
    0% { transform: translateX(0); }
    50% { transform: translateX(100px); }
    100% { transform: translateX(0); }
}
## Q10. What is Responsive Web Design? Explain Media Queries, CSS Variables, and Mobile-First Approach.
## Theory
1. Responsive Web Design: It means creating a website that looks good and works perfectly on all devices, whether it is a small mobile phone, a tablet, or a large desktop screen.
2. Media Queries: These are special CSS rules that apply styles only if certain conditions are met, like if the screen size is smaller than 768px, change the layout from 3 columns to 1 column.
3. CSS Variables: These are custom properties that allow us to store a value (like a specific color) in one place and reuse it everywhere in the CSS file. If we change it once, it updates everywhere automatically.
4. Mobile-First Approach: This is a strategy where we write CSS styles for small mobile screens first by default, and then use Media Queries to add complex layouts for bigger laptop and desktop screens later.
/* 1. CSS Variable */
:root {
    --main-color: darkblue;
}

/* Default style for Mobile Screens */
body {
    background-color: lightgray;
    font-size: 14px;
}

h1 {
    color: var(--main-color);
}

/* 2. Media Query for Desktop Screens (larger than 768px) */
@media (min-width: 768px) {
    body {
        background-color: white; /* Changes background on big screens */
        font-size: 18px;         /* Makes text bigger on desktop */
    }
}