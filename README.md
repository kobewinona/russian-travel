# Russian Travel

[![project](https://svgshare.com/i/p66.svg "github profile")](https://kobewinona.github.io/russian-travel/)

| [![github profile](https://svgshare.com/i/p5A.svg "github profile")](https://github.com/kobewinona) | &copy; dima klimkin |
| :---: | :---: |

| html | css | vscode | git | bem |
| :---: | :---: | :---: | :---: | :---: |
| [![html](https://svgshare.com/i/p7U.svg)](https://www.w3.org/html/) | [![css](https://svgshare.com/i/p6o.svg)](https://www.w3schools.com/css/) | [![vs code](https://svgshare.com/i/p5n.svg)](https://code.visualstudio.com/) | [![git](https://svgshare.com/i/p6d.svg)](https://git-scm.com/) | [![bem](https://svgshare.com/i/p6x.svg)](https://en.bem.info/) |

## about this project

This project helped me to understand adaptive, flexible and responsive design. I've learnt a lot from building this small page.

The webpage itself is about travelling in Russia and its beauties.

## CSS syntax decoration I used in this project

To make the code more readable for me I decided to devide rules by their function:

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

### **1st** block of lines describes an object in generall:

```css
dev {
  width: 0;
  min-height: 0;
  box-sizing: border-box;
  overflow: hidden;
}
```
>etc.

### **2nd** block of lines describes text and its decoration:

```css
dev {
  color: #fff;
  font-size: 14px;
  font-weight: normal;
  text-align: center;
}
```
>etc.

### **3rd** block of lines describes an object's content layout:

```css
dev {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  column-gap: 0;
}
```
>etc.

### **4th** block of lines describes an object's position and size:

- *rules' order goes from the furthest* ❏ *to the closest* ■ *to content*

- *rules with sides*  *go from top to the left* ↻

```css
dev {
  position: absolute;
  top: 0;
  right: 0;
  margin: 0;
  border: none;
  padding: 0;
}
```
![position](https://i.postimg.cc/HkN8sKfB/element.png)

### **5th** block of lines is just ```z-index``` ☺.

Inside those made-up blocks of lines I also try to maintain a certain order but sometimes I fail and it's not like anyone will ever see this anyway)

## styling of this project
*This is here just so I could add those cool bubbles with colors.*

**font**

```css
font-family: 'Inter', sans-serif;
```

**colors**

| dark grey (background) | black (text) |
| :---: | :---: |
| color: #2a2c2f | color: #fff |

## difficulties during this project

**1 problem**

Tag ```<picture>``` creates a small margin based on font-size:

![margin](https://i.postimg.cc/xCrTrDXX/margin.png)
*margins beetwen an element in ```<picture>``` and ```<p>``` without specifying ```font-size```*

![no-margin](https://i.postimg.cc/brgz2Z3n/no-margin.png)
*margins beetwen an element in ```<picture>``` and ```<p>``` with specifying ```font-size```*

**solution**

>specifying ```font-size``` to 0 helps:
```css
.lead__image-container {
  width: 100%;
  font-size: 0;

  position: relative;

  margin: 40px auto 0 auto;
}
```

**2 problem**

For some reason text in a browser doesn't wrap the way it does in a design template, even though all the parametres are specified in a markup.

![template-wrap](https://i.postimg.cc/QCh8tQks/template-wrap.png)
*the second word is taking another line to fit the box it is in.*

![no-wrap](https://i.postimg.cc/59S9rrbt/no-wrap.png)
*the second word stays in one line with the first word.*

The problem persists in **Chrome**, **FireFox** and **Safari**.

**no solution ☹**

## mobile-first vs desktop-first

I started building the website **desktop-first** but soon figured out that the code becomes so messy with media queris.
1. The fact that you need to add 1 to a resolution you make a query for is confusing. Doing this kind of math when browsing through the code is too tiresome (*but then again I might do something wrong* ☺).
2. The fact that width declared in a query does not help you to identify for what screen this query is for is so confusing.

```css
@media (max-width: 767px) {

}
```

>first you need to make an addition of 1 and 767 to get that this break-point is for screens of 768px and higher.

>second this query is not for tablets as the number of pixels may suggest but for mobile screens.

In addition to the mess above I sometimes had to use ```(min-width: 1280px)``` to set up a markup for wider screens, so chosing desktop-first you start a website kind of in-between resolutions and you just have to write more code to make it clear for a browser.

So I quickly switched to **mobile-first** and the code is so much cleaner.

```css
@media (min-width: 320px) {

}
```

>This is for mobile screens from 320px as the name clearly suggests.

```css
@media (min-width: 768px) {

}
```

>This is for tablet screens from 768px as the name clearly suggests.

```css
@media (min-width: 1024px) {

}
```

>This is for desktop screens from 1024px to infinity of beautiful pixels.

| thanks to yandex practicum team | [![yandex praktikum](https://svgshare.com/i/p77.svg)](https://practicum.yandex.ru/) | ♥ |
| :---: | :---: | :---: |
