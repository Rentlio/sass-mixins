Some scss mixins used for Rentl.io homepage and web app.

## SCSS Mixins

### @font
Font shorthand
<br>
[View Source](https://github.com/Rentlio/sass-mixins/blob/master/mixins/_font.scss)
```scss
/*
Source:
@mixin font($size: false, $weight: false, $style: false, $lh: false, $colour: false)
*/

// Example
@include font($fontSize-M, $fontWeight-regular, $fontStyle-normal, $fontSpacing-paragraph, $black);
```
### @push-auto
Horizontally center block level elements
<br>
[View Source](https://github.com/Rentlio/sass-mixins/blob/master/mixins/_push-auto.scss)
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
<br>
[View Source](https://github.com/Rentlio/sass-mixins/blob/master/mixins/_mq.scss)
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

### @z
Reason about z-index order, never again write `z-index: 999999999`
<br>
[View Source](https://github.com/Rentlio/sass-mixins/blob/master/mixins/_z.scss)
```scss
/*
Source:
@function z($name)
*/

// Example
$z-indexes: (
  'header',
  'body',
  'footer'
);

.header {
  z-index: z('header'); // 3
}
.body {
  z-index: z('body'); // 2
}
.footer {
  z-index: z('footer'); // 1
}
```

### @background-image
Background image helper with retina and SVG support
<br>
[View Source](https://github.com/Rentlio/sass-mixins/blob/master/mixins/_background-image.scss)
```scss
/*
Source:
@mixin background-image($name, $size: 100% auto, $repeat: no-repeat)
*/

// Example
@include background-image('Pattern');

/*
// Output:
// If there is svg file
background-image: url('Pattern.svg');

// No svg file but retina screen
background-image: url('Pattern@2x.png');

// No svg file and non retina screen
background-image: url('Pattern.png');
*/
```

### @readable-text
Render typography equally in all browsers
<br>
[View Source](https://github.com/Rentlio/sass-mixins/blob/master/mixins/_readable-text.scss)
```scss
/*
Source:
@mixin readable-text
*/

// Example
@include readable-text;
```

### @omega-reset
Specific for Neat grid framework. Reset `@omega` rules
<br>
[View Source](https://github.com/Rentlio/sass-mixins/blob/master/mixins/_omega-reset.scss)
```scss
/*
Source:
@mixin omega-reset($nth)
*/

// Example
@include omega-reset(3n);
```

### @grid-row, @grid-col, @grid-shift
Minimal grid system
<br>
[View Source](https://github.com/Rentlio/sass-mixins/blob/master/mixins/_grid.scss)
```scss
/*
Source:
@mixin grid-row($gutter: $grid-gutter)
@mixin grid-col($width: false)
@mixin grid-shift($width: 0)
*/

// Simple example
.grid {
  @include grid-row();
 
  .col-6 {
    @include grid-col(6 / 12);
  }
 
  .shift-1 {
    @include grid-shift(1 / 12);
  }
}

// Advanced example (build your own class helpers)
$grid-columns: 12;
$grid-gutter : 1em;
$breakpoint  : 768px;

.grid {
  @include grid-row($grid-gutter);
  
  @for $i from 1 through $grid-columns {
    .col-#{$i} {
      @include grid-col($i / $grid-columns);
    }
    
    .shift-#{$i} {
      @include grid-shift($i / $grid-columns);
    }
  }
  
  @media only screen and (max-width: $breakpoint) {
    > * {
      @include grid-col(1);
      @include grid-shift(0);
    }
    
    @for $i from 1 through $grid-columns {
      .col-#{$i} {
        @include grid-col(1);
      }
      
      .shift-#{$i} {
        @include grid-shift(0);
      }
    }
  }
}
```

## Contribution

Ready to submit a fix or a feature? Submit a pull request! And _please_:

- Update documentation comments where applicable.
- Maintain the existing style.

## Contact

- [Juraj Hilje](https://github.com/jurajhilje), [@juraj_hilje](https://twitter.com/juraj_hilje)

## License
See [LICENSE](https://github.com/Rentlio/sass-mixins/blob/master/LICENSE.md).