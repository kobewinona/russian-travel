[![cover](images/readme/cover.png)](https://kobewinona.github.io/russian-travel/)

# Russian Travel

[![Dima Klimkin Profile Page](https://img.shields.io/badge/Dima_Klimkin-f9f9f9?style=for-the-badge&logoColor=000&logo=github)](https://github.com/kobewinona)
[![Russian Travel Gh-Pages Page](https://img.shields.io/badge/GitHub_Pages-Russian_Travel-f9f9f9?style=for-the-badge&logo=githubpages)](https://kobewinona.github.io/russian-travel/)

[![HTML5](https://img.shields.io/badge/HTML5-f9f9f9?style=for-the-badge&logo=HTML5)](https://dev.w3.org/html5/spec-LC/)
[![CSS3](https://img.shields.io/badge/CSS3-f9f9f9?logoColor=264BDC&style=for-the-badge&logo=CSS3)](https://www.w3.org/TR/CSS/#css)
[![Git](https://img.shields.io/badge/Git-f9f9f9?style=for-the-badge&logo=git)](https://git-scm.com)
[![BEM](https://img.shields.io/badge/BEM-f9f9f9?logoColor=black&style=for-the-badge&logo=bem)](https://en.bem.info/methodology/)

[![Visual Studio Code](https://img.shields.io/badge/Visual_Studio_Code-f9f9f9?style=for-the-badge&logoColor=0066b8&logo=visualstudiocode)](https://code.visualstudio.com)

## contents

- [about this project](#about-this-project)
- [what I learned doing this project](#what-I-learned-doing-this-project)
- [mobile-first vs desktop-first](#mobile-first-vs-desktop-first)
- [CSS syntax decoration I used in this project](#CSS-syntax-structure-I-used-in-this-project)
- [problems I encountered doing this project](#problems-I-encountered-doing-this-project)
    - [problem #1](#problem)

## about this project

This project was a great opportunity for me to delve into the world of adaptive, flexible, and responsive design. I learned a lot about media queries and how they can be used to build a website that looks great on any device.

Through this project, I was able to gain a deeper understanding of these design principles and how they can be used to create a website that is both visually appealing and user-friendly. The website I created is all about the beauty of travelling in Russia, featuring stunning photos and informative articles about some of the most interesting places to visit. I hope that visitors to the site will find it both engaging and informative, and that it will inspire them to explore all that Russia has to offer.

## what I learned doing this project

As I worked on this project, I discovered that adaptive design allows a website to adapt to the user's screen size, while flexible design makes use of fluid grids and flexible images to ensure that the website looks great on any device. Responsive design, on the other hand, combines the best of both worlds to create a website that not only looks great, but also functions well on all devices.

## mobile-first vs desktop-first

When I began building the website, I started with a `desktop-first` approach, but soon realized that the code became very messy with media queries. One major issue was that I had to do some math to add 1 to a resolution when making a query, which was both confusing and tiresome to browse through. Another issue was that the width declared in a query didn't help me identify which screen the query was for.

```css
@media (max-width: 767px) {}
```
*So here first you need to make an addition of `1` and `767` to get that this breakpoint is for screens of `768px` and higher. Second this query is not for tablets as the number of pixels may suggest but for mobile screens.*

Additionally, I sometimes had to use `(min-width: 1280px)` to set up a markup for wider screens, resulting in a website that was kind of in-between resolutions. This made it necessary to write more code just to make it clear for the browser. So, I quickly switched to a `mobile-first` approach, resulting in much cleaner code.

```css
@media (min-width: 320px) {}
```
*This is for tablet screens from `320px` and higher as the name clearly suggests.*

```css
@media (min-width: 768px) {}
```
*This is for tablet screens from `768px` and higher as the name clearly suggests.*

```css
@media (min-width: 1024px) {}
```
*This is for desktop screens from `1024px` to `infinity` of beautiful pixels.*

I hope this makes sense and is helpful!

## CSS syntax structure I used in this project

To make the code more readable for me, I decided to divide rules by their function:

```css
.header__title {
  width: 730px;

  font-size: 102px;
  font-weight: 600;
  line-height: 96px;

  position: relative;
  margin: 0 0 0 64px;

  z-index: 2;
}
```

**1st** block of lines describes an object in general:

```css
div {
  width: 0;
  min-height: 0;
  box-sizing: border-box;
  overflow: hidden;
}
```

**2nd** block of lines describes text and its decoration:

```css
div {
  color: #fff;
  font-size: 14px;
  font-weight: normal;
  text-align: center;
}
```

**3rd** block of lines describes an object's content layout:

```css
div {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  column-gap: 0;
}
```

**4th** block of lines describes an object's position and size:

- *rules' order goes from the furthest* ❏ *to the closest* ■ *to content*

- *rules with sides*  *go from top to the left* ↻

```css
div {
  position: absolute;
  top: 0;
  right: 0;
  margin: 0;
  border: none;
  padding: 0;
}
```

**5th** block of lines is just `z-index` ☺.

Within these rules I try to maintain a certain order (still I sometimes fail).

## problems I encountered doing this project

### problem

Tag `<picture>` creates a small margin based on font-size:

![margin](https://i.postimg.cc/xCrTrDXX/margin.png)
*margins between an element in `<picture>` and `<p>` without specifying `font-size`*

![no-margin](https://i.postimg.cc/brgz2Z3n/no-margin.png)
*margins between an element in `<picture>` and `<p>` with specifying `font-size`*

#### solution

specifying `font-size` to `0` helps:

```css
.lead__image-container {
  width: 100%;
  font-size: 0;

  position: relative;

  margin: 40px auto 0 auto;
}
```

---

&hearts; thanks to yandex practicum team