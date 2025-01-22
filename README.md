# HTML and CSS Fundamentals Guide

A beginner's guide to understanding the basics of HTML and CSS for web development.

## Table of Contents
- [HTML Basics](#html-basics)
- [CSS Basics](#css-basics)
- [Layout and Positioning](#layout-and-positioning)
- [Responsive Design](#responsive-design)
- [Best Practices](#best-practices)

## HTML Basics

### Document Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Webpage</title>
</head>
<body>
    <!-- Content goes here -->
</body>
</html>
```

### Common HTML Elements

#### Text Elements
```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
<p>This is a paragraph.</p>
<strong>Bold text</strong>
<em>Italic text</em>
```

#### Lists
```html
<!-- Unordered List -->
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
</ul>

<!-- Ordered List -->
<ol>
    <li>First item</li>
    <li>Second item</li>
</ol>
```

#### Links and Images
```html
<a href="https://example.com">Click here</a>
<img src="image.jpg" alt="Description of image">
```

#### Containers
```html
<div>Generic container</div>
<section>Thematic grouping of content</section>
<article>Self-contained content</article>
<header>Header content</header>
<footer>Footer content</footer>
```

#### Forms
```html
<form>
    <label for="username">Username:</label>
    <input type="text" id="username" name="username">
    
    <label for="password">Password:</label>
    <input type="password" id="password" name="password">
    
    <button type="submit">Submit</button>
</form>
```

## CSS Basics

### CSS Syntax
```css
selector {
    property: value;
}
```

### Selectors
```css
/* Element Selector */
p {
    color: blue;
}

/* Class Selector */
.highlight {
    background-color: yellow;
}

/* ID Selector */
#header {
    font-size: 24px;
}

/* Descendant Selector */
div p {
    margin: 10px;
}
```

### Box Model
Every element in HTML has a box model:
```css
.box {
    /* Inside to outside */
    padding: 10px;     /* Space inside the border */
    border: 1px solid black;
    margin: 20px;      /* Space outside the border */
}
```

### Common CSS Properties
```css
.element {
    /* Typography */
    font-family: Arial, sans-serif;
    font-size: 16px;
    font-weight: bold;
    color: #333333;
    
    /* Spacing */
    margin: 10px;
    padding: 15px;
    
    /* Colors and Background */
    background-color: #ffffff;
    color: #000000;
    
    /* Border */
    border: 1px solid #cccccc;
    border-radius: 5px;
}
```

## Layout and Positioning

### Display Property
```css
/* Block elements (take full width) */
.block {
    display: block;
}

/* Inline elements (take content width) */
.inline {
    display: inline;
}

/* Inline-block (mix of both) */
.inline-block {
    display: inline-block;
}
```

### Flexbox
```css
/* Parent (Flex Container) */
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
}

/* Children (Flex Items) */
.item {
    flex: 1;
}
```

Example use case:
```html
<div class="container">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
</div>
```

### Grid
```css
/* Parent (Grid Container) */
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

/* Children (Grid Items) */
.grid-item {
    grid-column: span 2; /* Takes up 2 columns */
}
```

## Responsive Design

### Media Queries
```css
/* Mobile First Approach */
.container {
    width: 100%;
    padding: 10px;
}

/* Tablet */
@media (min-width: 768px) {
    .container {
        width: 750px;
        margin: 0 auto;
    }
}

/* Desktop */
@media (min-width: 1024px) {
    .container {
        width: 960px;
    }
}
```

### Flexible Images
```css
img {
    max-width: 100%;
    height: auto;
}
```

## Best Practices

### 1. HTML Best Practices
- Use semantic HTML elements (`<header>`, `<nav>`, `<main>`, `<footer>`)
- Include proper meta tags
- Write descriptive `alt` attributes for images
- Keep your code indented and organized

### 2. CSS Best Practices
- Use a consistent naming convention (e.g., BEM)
- Write mobile-first media queries
- Avoid using !important
- Group related properties together
- Use CSS variables for reusable values:
```css
:root {
    --primary-color: #007bff;
    --secondary-color: #6c757d;
    --spacing-unit: 8px;
}

.button {
    background-color: var(--primary-color);
    padding: var(--spacing-unit);
}
```

### 3. Performance Best Practices
- Minify CSS and HTML in production
- Optimize images
- Use appropriate image formats
- Combine and compress files

## Common CSS Units

### Absolute Units
- `px` - pixels
- `pt` - points
- `cm` - centimeters
- `in` - inches

### Relative Units
- `em` - relative to parent font-size
- `rem` - relative to root font-size
- `%` - percentage relative to parent
- `vw` - viewport width
- `vh` - viewport height

## Example Project

Here's a simple example combining various concepts:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <style>
        /* CSS Variables */
        :root {
            --primary-color: #007bff;
            --text-color: #333;
            --spacing: 20px;
        }

        /* Basic Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
        }

        /* Header Styles */
        header {
            background-color: var(--primary-color);
            color: white;
            padding: var(--spacing);
        }

        /* Navigation */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: var(--spacing);
        }

        /* Main Content */
        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: var(--spacing);
            padding: var(--spacing);
        }

        .project-card {
            border: 1px solid #ddd;
            padding: var(--spacing);
            border-radius: 8px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 10px;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>My Portfolio</h1>
    </header>

    <nav>
        <a href="#home">Home</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
    </nav>

    <main class="projects">
        <div class="project-card">
            <h2>Project 1</h2>
            <p>Description of project 1</p>
        </div>
        <div class="project-card">
            <h2>Project 2</h2>
            <p>Description of project 2</p>
        </div>
        <div class="project-card">
            <h2>Project 3</h2>
            <p>Description of project 3</p>
        </div>
    </main>
</body>
</html>
```

## Additional Resources

- [MDN Web Docs](https://developer.mozilla.org/)
- [CSS-Tricks](https://css-tricks.com/)
- [W3Schools](https://www.w3schools.com/)
- [Can I Use](https://caniuse.com/)

## Practice Tips

1. Start with simple projects
2. Use browser dev tools to inspect and modify CSS
3. Build responsive layouts
4. Experiment with different properties
5. Learn CSS Flexbox and Grid thoroughly
6. Practice recreating existing website layouts

Remember: The best way to learn is by doing. Start building projects and experiment with different properties and values to see how they work together.
