# MicroCSS

_Expanding upon the [ideals](https://picocss.com/#:~:text=graceful%C2%A0and%C2%A0simple,-!) of [picoCSS](https://picocss.com), with icons and helper variables_

### Adds:

* [open-props](https://open-props.style) for quick variables
* [open-color](https://yeun.github.io/open-color/) for nice colors and custom themes
* [micro](https://github.com/octoshrimpy/microcss/blob/main/_micro.scss): my own personal overrides to pico and open-props, with sane defaults and batteries included
  * [elevation shadows](https://material.io/design/environment/elevation.html) from [Material Design Language](https://material.io/design/foundation-overview)
    * inset shadows
    * outset shadows
    * proper css transitions between inset and outset
  * [nerdfont icons](https://nerdfonts.com) with easy classes within `.icon i` elements - search the [cheatsheet](https://www.nerdfonts.com/cheat-sheet)! ([icons here](./_nf.css))
  * simple-to-use breakpoints mixin by [@kittyGiraudel](https://twitter.com/KittyGiraudel) (SCSS only). see [usage here](https://css-tricks.com/snippets/sass/mixin-manage-breakpoints/)
    * > 💡 *css-only* custom media queries [are on their way](https://www.stefanjudis.com/notes/can-we-have-custom-media-queries-please/)!
  * inverse text color finder, from [Bulma.io](https://bulma.io/documentation/) (SCSS only). ([source](https://github.com/jgthms/bulma/blob/master/sass/utilities/functions.sass))
  
  
  Just include the [main file](./micro.css) as well as nerdfonts into your project with:
```css 
@import 'https://octoshrimpy.github.io/microcss/micro.css';
@import "https://octoshrimpy.github.io/microcss/nf.css";
```

It will import pico, open-props, and everything else you need!

---

## Moar Information

To optimize your styling and render cycles, consider using preload/prefetch for your css. more info on [this great post by DigitalOcean](https://www.digitalocean.com/community/tutorials/html-preload-prefetch)

Putting it all together:

```css
/* your main css file */


/* microcss
 * https://octoshrimpy.github.io/microcss */
 
@import 'https://octoshrimpy.github.io/microcss/micro.css';
@import "https://octoshrimpy.github.io/microcss/nf.css";


/* your code goes down here */

```

```html
<!-- within the <head> of your main HTML file where you import styles -->

<link
  rel="preload"
  as="style"
  onload="this.rel = 'stylesheet'"
  href='link/to/your/style.css'>

<!-- load even if javascript is disabled -->
<noscript>
  <link
    rel="stylesheet"
    href='link/to/your/style.css'>
</noscript>

```
