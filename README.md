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

---
## S3V1 - What is SMACSS?

#### Base Rules:
define what elements look like by default

#### Layour Rules:
define layout styles for major sections of a page

#### Module Rules:
where styles are written for each module as stand-alone, reusable components

#### State Rules:
define styles for element states

#### Theme Rules:
define different colors and images to give project a different theme
 
## S3V2 - SMACSS in our workflow

## Quiz 
### Question 1 / 5

What are the five types of SMACSS categories?

*base, layout, modules, states and themes*

### Question 2 / 5

The ** rules make up the majority of a project's styles.

### Question 3 / 5

Is SMACSS a framework?

*No, SMACSS is a style guide for organizing our code*

### Question 4 / 5

The CSS reset styles fall under which category?

*Base rules*

### Question 5 / 5

Which rules define what elements look like by default?

*Base rules*

## S3V3 - Panel Layout Component 
## S3V4 - Styling Images

## Quiz 
### Question 1 / 5

Which of the following statements about writing Sass is true?

*Our ruleset should only inherit and add to previous rules*  &  *We shouldn't need to undo properties*

### Question 2 / 5

Is it important to closely follow all of SMACSS' guidelines?

*No, use the suggestions and guidelines to help find what works for you.*

### Question 3 / 5

Why is it a good idea to include an index/manifest file in each directory?

*It makes our Sass more manageable because we only need to import the single index reference from each directory.*

### Question 4 / 5

In the layout directory:

*we define the layout styles for all the major components of our project.*

### Question 5 / 5

Which of the following are major layout components of a page?

*header, sidebar, grid*
---

## S4V1 - Grid Configuration
## S4V2 - Generating Column Classes
## S4V3 - Column Layout

## Challenge
### Task 1 / 3

First, use a `@for` directive to write a loop that iterates through each column defined in the `$cols` variable, starting from 1.

```scss
@for $i from 1 through $cols {

}
```
### Task 2 / 3

Next, we'll need to output selectors for the total number of columns. Inside the @for rule, create a rule that passes the `$i` variable as the modifier in the `.grid__col--`selector.

```scss
@for $i from 1 through $cols {
    .grid__col--#{$i} {
        
    }
}
```
### Task 3 / 3

Finally, to output the width value of each column, use Sass' `percentage` function to return the result of `$target / $context` as a percentage. Use `($width * $i) + ($gutter * ($i - 1))` as the value for `$target`.

```scss
@for $i from 1 through $cols {
    $target: ($width * $i) + ($gutter * ($i - 1));

    .grid__col--#{$i} {
        width: percentage($target / $context);
    }
}
```

## S4V4 - Building the Grid Container

## Quiz 
### Question 1 / 3

By default, are we able to extend a selector from within a @media query?

*No*

### Question 2 / 3

What does the `$i` variable in a loop usually mean?

*$i is a counter variable that iterates through each item in a list or variable.*

### Question 3 / 3

The `$context` variable is scoped to the loop, so it's unable to pass a value in the `.grid__col` rule. Which flag will allow you to use the `$context` variable anywhere.

// Column loop
@for $i from 1 through $cols {
  $context: context($w, $cols, $gutter);
  $target: ($w * $i) + ($gutter * ($i - 1));
  .grid__col--#{$i} {
    width: percentage($target/$context);
  }
}
.grid__col {
  margin-left: percentage($gutter/$context);
}

*!global*