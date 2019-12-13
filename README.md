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


