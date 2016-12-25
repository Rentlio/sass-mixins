Rentl.io Sass Mixins
==============

Some scss mixins used for Rentl.io homepage and web app.

### @font
Font shorthand
```scss
/*
Source:
@mixin font($size: false, $weight: false, $style: false, $lh: false, $colour: false)
*/

// Example
@include font($fontSize-M, $fontWeight-regular, $fontStyle-normal, $fontSpacing-paragraph, $black);
```
### @push-auto
Center block level elements
```scss
/*
Source:
@mixin push-auto
*/

// Example
@include push-auto;
```