# typo-helper
Sass helper for managing typography components on projects

## Getting Started
to be defined

## Usage

### font-face
To simplify the font import with `@font-face` a mixin is available, you can use it as below:

```
@include font-face($name, $path, $weight: normal, $style: normal, $exts: eot woff2 woff ttf svg);
```

The font-family name and path are required, but the weight, the style and the extentions to import into the font-face have those default values.


#### Example
```
@include font-face('my font', '../fonts/myfont', '400', italic, ttf);
```

### font-family
You can set a map with a bunch of couple key, value for generating as many helper classes for setting a font-family to a selector.
The default value for the `$font-family__list` variable is:
```
$font-family__list: (
    'serif': 'Times New Roman, Bodoni, Garamond, Minion Web, ITC Stone Serif, MS Georgia, Bitstream Cyberbit',
    'sans-serif': 'MS Trebuchet, ITC Avant Garde Gothic, MS Arial, MS Verdana, Univers, Futura, ITC Stone Sans, Gill Sans, Akzidenz Grotesk, Helvetica',
    'cursive': 'Caflisch Script, Adobe Poetica, Sanvito, Ex Ponto, Snell Roundhand, Zapf-Chancery',
    'fantasy': 'Alpha Geometrique, Critter, Cottonwood, FB Reactor, Studz',
    'monospace': 'Courier, MS Courier New, Prestige, Everson Mono',
) !default;
```
This will create a class `.font-family--serif` with for rule `font-family: Times New Roman, Bodoni, Garamond, Minion Web, ITC Stone Serif, MS Georgia, Bitstream Cyberbit` and etc for each occurence of the `$font-family__list` map.

If you want to change the prefix of the generated class you can by resetting the variable `$font-family__selector-prefix` set as default as below:
```
$font-family__selector-prefix: 'font-family--' !default;
```

There is also a class generated for the `inherit` value of the `font-family` property. The `.font-family--inherit` is generated by default but you can turn it of by switching to false the variable `$font-family__include--inherit`.

You can avoid typo-helper to generate any helper font-family helper class by switching to false the `$font-family` variable.
