# Frontend Mentor - Article preview component solution

This is a solution to the [Article preview component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/article-preview-component-dYBN_pYFT). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- See the social media share links when they click the share icon

### Screenshot

Desktop design:
![](./design/desktop-design.jpg)
Desktop active state:
![](./design/desktop-active-state.jpg)

Mobile design:

![](./design/mobile-design.jpg)

Mobile active state:

![](./design/mobile-active-state.jpg)

### Links

- Solution URL: [solution URL here](https://github.com/ernur-burshak/Article-preview-component)
- Live Site URL: [live site URL here](https://ernur-burshak.github.io/Article-preview-component/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow
- JS

### What I learned

In this project, I learned how to manipulate DOM when clicking a button using JS and apply some new CSS styles.

```html
<script
  type="module"
  src="https://cdn.jsdelivr.net/npm/ionicons@latest/dist/ionicons/ionicons.esm.js"
></script>
<script
  nomodule
  src="https://cdn.jsdelivr.net/npm/ionicons@latest/dist/ionicons/ionicons.js"
></script>
<script src="scripts/main.js"></script>
```

```css
.share {
  position: relative;
}

.share-button {
  background: #ecf2f8;
  padding: 6px;
  border-radius: 20px;
  font-size: 20px;
  color: #6e8098;
  transition: all 0.25s ease;
}

.share-button:hover,
.share-button.active {
  background: #6e8098;
  color: #ecf2f8;
}

.share-option {
  /**
   * variable for transforming `.share-option` box 
   * without repeating all transform value
   */
  --scale: 0;
  --translateX: -50%;
  --translateY: 0;

  background: #48556a;
  position: absolute;
  bottom: calc(100% + 28px);
  left: 50%;
  transform: translate(var(--translateX), var(--translateY)) scale(var(--scale));
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 17px 40px;
  border-radius: 10px;
  box-shadow: 0 5px 20px -5px #0003;
  transform-origin: bottom;
  visibility: hidden;
  transition: all 0.25s ease;
}

.share-option.active {
  --scale: 1;
  visibility: visible;
}

.share-option::after {
  content: "";
  background: hsl(217, 19%, 35%);
  width: 20px;
  height: 20px;
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translate(-50%, -60%) rotate(45deg);
}

.share-option ion-icon:hover,
.main-description:hover,
.author-name:hover {
  filter: invert(1);
}
```

```js
const shareOption = document.querySelector(".share-option");

document.querySelector(".share-button").addEventListener("click", function () {
  this.classList.toggle("active");
  shareOption.classList.toggle("active");
});
```

### Continued development

In the future, I want to practice DOM manipulation more.

### Useful resources

- [resource 1](https://www.frontendmentor.io/) - It always helps to find a good practice.
- [resource 2](https://www.youtube.com/) - helped me understand the basics of JS.
- [resource 3](https://discord.com/) - helped when I couldn't find a solution.

## Author

- Website - [Ernur](https://ernur-burshak.github.io/Article-preview-component/)
- Frontend Mentor - [@ernur-burshak](https://www.frontendmentor.io/profile/ernur-burshak)
- Linkedin - [Ernur Burshak](https://www.linkedin.com/in/ernur-burshak-7b6b0b31b?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app)

## Acknowledgments

I always thank the Frontend Mentor platform for giving me a good practice.
I also want to thank you on the codewithsadee YouTube channel.
