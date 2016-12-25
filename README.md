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

### @mq
Media queries shorthand
```scss
/*
Source:
@mixin mq($size, $type: max, $orientation: width)
*/

// Example
$breakpoints: (
  'phone'       : 400px,
  'phone-wide'  : 480px,
  'phablet'     : 560px,
  'tablet-small': 640px,
  'tablet'      : 768px,
  'tablet-wide' : 1024px,
  'desktop'     : 1248px,
  'desktop-wide': 1440px
);

@include mq('phone') {
  font-size: 16px;
}
@include mq('tablet', min) {
  font-size: 20px;
}
@include mq(1000px, max, height) {
  font-size: 24px;
}
```