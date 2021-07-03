# Frontend Mentor - Profile card component solution

This is a solution to the [Profile card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/profile-card-component-cfArpWshJ). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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

- Build out the project to the designs provided

### Links

- Solution URL: [https://github.com/atran14/atd-profile-card-component-main](https://github.com/atran14/atd-profile-card-component-main)
- Live Site URL: [https://atran14.github.io/atd-profile-card-component-main/](https://atran14.github.io/atd-profile-card-component-main/)

## My process

### Built with

- Semantic HTML5 markup
- Flexbox
- CSS Grid
- Desktop-first workflow
- Sass

### What I learned
I played around a bit with CSS Grid layout system in this challenge. I haven't explored that much so I will keep continue doing that in the upcoming challenges.

Recreating the background using the two SVGs provided was quite a challenge for me. At first, I tried to arranged them using the "background" shorthand CSS attribute. Fiddling with it and trying to get it to work was one of the time-consuming tasks that I have to deal with in this challenge. In the end though, I ended up abandon that idea altogether and go with my second plan, which is to simply reposition the two SVG patterns, and have their container to have only the background color property applied instead.

The second thing that is also a bit of a hurdle this time for me was positioning the avatar picture to overlap with the card's top banner, and have its surrounding borders be white. I achieved that by using this bit of SCSS:
```scss
.avatar {
    $pic-dimensions: 5rem;
    $border-radius-width: 5px;

    position: relative;
    width: 100%;
    height: calc(#{$pic-dimensions} / 2 + #{$border-radius-width});

    &__pic {
      position: absolute;
      border-radius: 50%;
      height: $pic-dimensions;
      width: $pic-dimensions;
      object-fit: cover;

      top: -$pic-dimensions / 2;
      left: 50%;
      margin-left: -$pic-dimensions / 2;
      box-shadow: 0 0 0 #{$border-radius-width} white,
        inset 0 0 0 #{$border-radius-width} white,
        inset 0 0 0 #{$border-radius-width} white,
        inset 0 0 0 #{$border-radius-width} white,
        inset 0 0 0 #{$border-radius-width} white;
    }
  }
```
Notice that when the container's inner img tag has its position set to absolute, all of the contents below it will flow right to the top, since the img tag then will not create any gap. In order to take account of this, I have the container's height to be half the height of the avatar picture (plus its border) in order to have its below content only flow up to just the point where the avatar picture ends.

### Continued development

I have only just relearnt about animations with CSS (particularly about keyframes and the like) so I would like to use that some time in my future projects to spice things up a bit with some fancyy-ness. 😜


### Useful resources

- [Albert Feynman profile card CodePen](https://codepen.io/AlbertFeynman/pen/YJGjmz) - This helped me for how to position the avatar picture and with its rounded border.

## Author

- Frontend Mentor - [@atran14](https://www.frontendmentor.io/profile/atran14)