# Developer's note

This is by no means a perfect solution. There are a ton of layout bugs I tried to fix but didn't have enough skills as of now. Most of the standard layout will work - Desktop, Tablet and Mobile.

# Frontend Mentor - Space tourism website solution

This is a solution to the [Space tourism website challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/space-tourism-multipage-website-gRWj1URZ3). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for each of the website's pages depending on their device's screen size
- See hover states for all interactive elements on the page
- View each page and be able to toggle between the tabs to see new information

### Links

- Solution URL: [Solution](https://www.frontendmentor.io/solutions/solution-space-tourism-website-qU5e3Aju97)
- Live Site URL: [Github](https://nerometa.github.io/space-tourism-website-challenge/)

## My process

### Built with

- Semantic HTML5 markup
- CSS, Flexbox and Grid
- JavaScript

### What I learned

First thing that come to mind is navbar and the styling of it. I didn't know that I can do glassmorphism with it - background blur and stuffs.

```html
<nav>
  <ul class="primary-navigation underline-indicators flex">
    <li class="active">
      <a class="text-white uppercase letter-spacing-2" href="#"
        ><span>00</span>Active</a
      >
    </li>
    <li>
      <a class="text-white uppercase letter-spacing-2" href="#"
        ><span>01</span>Hovered</a
      >
    </li>
    <li>
      <a class="text-white uppercase letter-spacing-2" href="#"
        ><span>02</span>Idle</a
      >
    </li>
  </ul>
</nav>
```

Which can be achieved with this:

```css
@supports (backdrop-filter: blur(1.5rem)) {
  .primary-navigation {
    background: hsl(var(--clr-white) / 0.09);
    backdrop-filter: blur(1.5rem);
  }
}
```

Another thing I like is the content in every page. So much was done with `display : grid`, especially when I started to put in content. With a little bit of work from `grid-template-area`, the content just stacked up easily.

```css
.grid-container--destination {
  --flow-space: 2rem;
  grid-template-areas:
    "title"
    "image"
    "tabs"
    "content";
}
```

Finally, Custom Properties and Utility Classes.

Oh. My. Goodness.

If I have no choice but to use CSS, I will gladly waste my time setting these things up. When combined with `@media`, it is so powerful.

Suppose you got some variables for font sizes:

```css
:root {
  /* font-sizes */
  --fs-900: clamp(5rem, 8vw + 1rem, 9.375rem);
  --fs-800: 3.5rem;
  --fs-700: 1.5rem;
  --fs-600: 1rem;
  --fs-500: 1rem;
  --fs-400: 0.9375rem;
  --fs-300: 1rem;
  --fs-200: 0.875rem;
}
```

In smaller screen, just use `@media` and there you go! instant smaller font size for smaller screens.

```css
@media (min-width: 35em) {
  :root {
    --fs-800: 5rem;
    --fs-700: 2.5rem;
    --fs-600: 1.5rem;
    --fs-500: 1.25rem;
    --fs-400: 1rem;
  }
}
```

### Continued development

I think grid is really, really useful here when you got a complex layout of content, but I don't grasp the fundamentals that much in this project. Some of the issues I have with it are content overflow and assign an area for a piece of content.

I'm definitely learning Sass/SCSS simply because I tried and I like how efficient it is. Utility Classes like I saw in this project can go straight to partial and `@use` it in my main Sass/SCSS file.

### Useful resources

[A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) - This helped me through CSS Grid. Nice and clear visuals.

## Author

- Website - [nerometa](https://github.com/nerometa/)
- Frontend Mentor - [@nerometa](https://www.frontendmentor.io/profile/nerometa)
