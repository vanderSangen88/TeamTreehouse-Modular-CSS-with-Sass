# TeamTreehouse-Modular-CSS-with-Sass

Install Sass:
`npm i -g sass`

Run Sass:
`sass --watch scss:css`

## S1V2 - The Project Config File

The `_config.scss`-file contains all the variables used in the project:
- Font Stacks
- Font Weights
- Descriptive Colors
- Color Usage
- Text

> Use [name-that-color](http://chir.ag/projects/name-that-color) to create more distinct names to use as variable-names.

## S1V3 - Pixels to Em Function

```scss
@function em($target, $context: $base__font-size) {
    @return ($target / $context) * 1em;
}
```

## S1V4 - Colors with Sass Maps
---
## S2V1 - The BEM Pattern
## S2V2 - Using BEM in our Project

## Quiz 
### Question 1 / 6

With BEM, element classes are usually prefixed with:

*two underscores*

### Question 2 / 6

With BEM, modifier classes are usually prefixed with:

*two hyphens*

### Question 3 / 6

One of the biggest advantages of using BEM convention is:

*We communicate what a block of HTML does just from it's naming convention, and selectors are easier to understand because we provide the context directly into the selector.*


### Question 4 / 6

Write a BEM element class for an item element that is a child of nav: *.nav__item*

### Question 5 / 6

BEM stands for:

*Block, Element, Modifier*

### Question 6 / 6

How would you write a BEM modifier class for an active variation of .nav__item?

*.nav__item--active*

## S2V3 - BEM Mixins 

A mixin for styling elements inside a block:
Pass the element-selector name
```scss
@mixin e($element) {
    &__#{$element} {
        @content;
    }
}
```
A mixin for styling modifiers inside an element:
Pass the element-selector name
```scss
@mixin m($modifier) {
    &--#{$modifier} {
        @content;
    }
}
```

> Placeholder selectors: Group selectors that share common base styles.

## Challenge
### Task 1 / 2

Use a parent selector reference to output the BEM class `.menu__link`. Set the color to `blue` and the padding to `.5em`.

```scss
.menu {
    margin: 1em 0;

    &__link {
        color: blue;
        padding: .5em;
    }
}
```
### Task 2 / 2

Next, use a parent selector reference to create a modifier class for the `active` variation of `.menu__link`. Set the color to `red`.

```scss
.menu {
    margin: 1em 0;

    &__link {
        color: blue;
        padding: .5em;

        &--active {
            color: red;
        }
    }
}
```

## S2V4 - Styling the Headlines 
## S2V5 - Headline Modifiers
## S2V6 - Styling Form Elements

## Quiz 
### Question 1 / 4

If an element can exist inside any module on the page without any context dependency, does it still need a BEM class name?

*No*

### Question 2 / 4

What is one of the advantages of using placeholder selectors with modifier classes?

*They prevent us from having to define both the element and the modifier class in the HTML*

### Question 3 / 4

Write the Sass directive that instructs the `.btn--submit` modifier class to inherit the base styles from `%btn-base`.

*@extend %btn-base*

### Question 4 / 4

How would we write the BEM modifier class for the last item in a menu block?

*.menu__item--end*
