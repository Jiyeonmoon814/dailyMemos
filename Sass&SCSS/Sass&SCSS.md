# Sass&SCSS

<br>

### Variables
>You can store things like colors,font stacks, or any CSS value you think you'll want to reuse.
>Sass uses the $ symbol to make something a variable. 

<br>

```SCSS
$font-stack: Helvetica, sans-serif;
$main-color: #333;

body {
font: 100% $font-stack;
color: $main-color;
}
```

<br>

### Nesting
>Sass will let you next your CSS selectors in a way that follows the same visual hierarchy of your HTML.
>Be aware that overly nexted rules will result in over-qualified CSS that could prove hard to maintain and 
>is generally considered bad practice.

<br>

```SCSS
$bgcolor : #c1c1c1;
#nested {
  bacground-color:$bgcolor;
  h3 {
    color:$main-color;
    }
  }
```

<br>

### Partials
>You can create partial Sass files that contain little snippets of CSS that you can include in otehr Sass files.
>This is a great way to modularize your CSS and help keep things easier to maintain. 
>A partial is a Sass file named with a leading underscore.
>The underscore lets Sass know that the file is only a partial file and that it should not be generated into a CSS file.
>Sass partials are used with the @use rule. 

<br>

```SCSS
// _base.css
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
```

<br>

```SCSS
// styles.scss
@use 'base';

.inverse {
  background-color: base.$primary-color;
  color: white;
}
```

<br>

### Mixins 
>A mixin lets you make groups of CSS declarations that you want to reuse throughout your site. 
>You can even pass in values to make your mixin more flexible. 

<br>

```SCSS
@mixin theme($theme:DarkGray){
  background: $theme;
  box-shadow: 0 0 1px rgba($theme, .25);
  color:#fff;
}

.info {
  @include theme;
  }
 
.alert {
  @include theme($theme:DarkRed);
}
```

<br>

>By using the variable $property inside the parentheses so we can pass in a transform of whatever we want.
>After you create your mixin, you can then use it as a CSS declaration starting with @include followed by the name of the mixin.

<br>

### Interpolation 
>Interpolation can be used almost anywhere in a Sass stylesheet to embed the result of a SassScript expression into a chunk of CSS. 
>Just wrap an expression in #{} in any of the following places:
> >Selectors in style rules





   