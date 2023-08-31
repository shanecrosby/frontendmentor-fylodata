# Frontend Mentor - Fylo data storage component solution

This is a solution to the [Fylo data storage component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/fylo-data-storage-component-1dZPRbV5n). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size

### Links

- Solution URL: [Github](https://github.com/shanecrosby/frontendmentor-fylodata)
- Live Site URL: [Github Pages](https://shanecrosby.github.io/frontendmentor-fylodata/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

This one was trickier than my first one, especially trying to keep the elements correctly positioned while making the page responsive. I think use of javascript might help with the bar graph - especially the positioning of the end marker. It would likely be necessary anyway if this were hooked up to show the live stats of a cloud storage system.

Triangles can be created using a zero height/width div with a large border.
The use a thick transparent border on the sides perpendicular to the direction you want the arrow to face,
and a thick coloured border on the side opposite the direction you want the arrow to face.
E.g. a left-pointing arrow uses a right border, with transparent top and bottom.

```css
.triangle {
  width: 0;
  height: 0;
  border-top: 30px solid transparent;
  border-bottom: 30px solid transparent; 
  border-right:30px solid white; 
}
```

You can pin an element on a responsive element by using flexbox. Create a flex container with row-reverse, aligining items to the top (flex-start).
On the responsive div, use the calc() function to set the maximum width to subtract the width of the pinned element.

```html
<div class="container">
  <div id="responsiveDiv">
    <!-- Content of the responsive div -->
  </div>
  <div id="fixedDiv">
    <!-- Content of the fixed div -->
  </div>
</div>
```

```css
.container {
  display: flex;
  flex-direction: row-reverse; /* Reverse the order of divs */
  align-items: flex-start; /* Align items to the top */
}

#responsiveDiv {
  flex: 1; /* Take up remaining space */
  max-width: calc(100% - <fixedDivWidth>); /* Adjust based on your fixed div's width */
  /* Rest of your responsive styles */
}

#fixedDiv {
  width: <fixedDivWidth>;
  /* Other styles for the fixed div */
}
```
Thanks to ChatGPT for the assist on this one.
"Replace <fixedDivWidth> with the actual width of your fixed div. The key here is to use flexbox to create a layout where the responsive div takes up the remaining space, and the fixed div is given a fixed width. The flex-direction: row-reverse; ensures that the fixed div is on the right side.

With this setup, the responsive div will change its width based on the viewport size, and the fixed div will stay positioned to the right of it.

Remember that achieving complex layouts in CSS without JavaScript might require some experimentation and tweaking, depending on your specific requirements and design. Always test thoroughly on different devices and browsers to ensure the desired behavior."

### Useful resources

- [ChatGPT](https://chat.openai.com) - AI language models are the future of web programming. While I think it is essential to understand the code you're using and how it works, AI models like GPT can be invaluable in helping to identify bugs and provide assistance in understanding concepts and techniques one might not be fully experienced in.


## Author

- Website - [Shane Crosby](https://www.shanecrosby.com)
- Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/shanecrosby)
- Twitter - [@crosbyshane](https://www.twitter.com/crosbyshane)
