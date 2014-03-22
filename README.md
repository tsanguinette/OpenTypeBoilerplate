# OpenType Mixin Boilerplate
A preprocessor boilerplate to easily use and control OpenType features in webfonts. This Git is an addition to a thesis project which promotes and educates OpenType features in webfonts through the W3C lower-level `font-feature-settings` CSS property.

* Author: Tyler Sanguinette 2013-2014
* Contributor: Jorge Colindres 2014
* License: MIT

**Thesis Project:** [http://typequest.org](http://typequest.org/)
**Thesis Presentation:** [http://talk.typequest.org](http://talk.typequest.org)

## Purpose
The purpose of this boilerplate is to help make a faster workflow for developers and designers who want to control fine typographic detail with SCSS, LESS and Stylus but do not want to write the large amount of code (browser prefixes) to produce it.

## Explanation of CSS Feature
There are three parts to the CSS feature:

`-webkit-font-feature-settings` *Browser prefix*
`"liga"` *The OpenType feature*
`1` *1 for display and 0 for do NOT display*

`-webkit-font-feature-settings: "liga" 1;`

## LESS Variables
Variable names are based on the OpenType code used by Type designers when creating OpenType data tables. The `font-feature-settings` understands these features and makes them possible.

```less
//Typographic Values
@liga: "liga" 1; //Ligatures
@dlig: "dlig" 1; //Discretionary Ligatures
@hlig: "hlig" 1; //Historical Ligatures
@clig: "clig" 1; //Contextual Ligatures
@smcp: "smcp" 1; //Small Caps
@c2sc: "c2sc" 1; //Small Caps from Caps
@cpsp: "cpsp" 1; //Capital Spacing
@titl: "titl" 1; //Titling Alternates
@lnum: "lnum" 1; //Lining Numbers
@onum: "onum" 1; //Old-style Numbers
@ordn: "ordn" 1; //Ordinals
@sups: "sups" 1; //Superscript
@subs: "subs" 1; //Subscript
@sinf: "sinf" 1; //Scientific Inferiors
@numr: "numr" 1; //Numerator
@dnom: "dnom" 1; //Denominator
@pnum: "tnum" 1; //Proportional Spacing
@tnum: "tnum" 1; //Tabular Spacing
@frac: "frac" 1; //Fractions
@afrac: "afrac" 1; //Alternate Fractions
@zero: "zero" 1; //Slashed Zero
@swsh: "swsh" 1; //Swash Alternates
@cswh: "cswh" 1; //Contextual Swash
@calt: "calt" 1; //Contextual Alternates
@hist: "hist" 1; //Historical Alternates
@salt: "salt" 1; //Stylistic Alternates
@c2sc: "c2sc" 1; //Small Capitals from Capitals
@c2pc: "c2pc" 1; //Petite Capitals from Capitals
@ss01: "ss01" 1; //Stylistic Set 1
@ss02: "ss02" 1; //Stylistic Set 2
@ss03: "ss03" 1; //Stylistic Set 3
@ss04: "ss04" 1; //Stylistic Set 4
@size: "size" 1; //Optical Size
@locl: "locl" 1; //Localized Forms
```

## LESS Markup pattern
The LESS boilerplate contains `@value`s up to 10. Which means you can have up to 10 typographic values in the same `font-feature-settings` to activate multiple features at once. Use values from the variable section. Note the difference between LESS and SCSS multiple values.

```less
h1{
  .font-feature-settings(@value);
}

h1{
  .font-feature-settings(@value, @value1);
}
```
## LESS Output and Use
To use this boilerplate simply declare the class you want to apply features to, call the class `.font-feature-settings` and then pass in the values (OpenType features) you need. Each example shows the LESS code on top followed by the preprocessed.

```less
//One value
h1{
  .font-feature-settings(@liga);
}

h1 {
  font-feature-settings: "liga" 1;
  -webkit-font-feature-settings: "liga" 1;
  -moz-font-feature-settings: "liga" 1;
  -o-font-feature-settings: "liga" 1;
  -ms-font-feature-settings: "liga" 1;
}


//Two values
h1{
  .font-feature-settings(@liga, @smcp);
}

h1 {
  font-feature-settings: "liga" 1, "smcp" 1;
  -webkit-font-feature-settings: "liga" 1, "smcp" 1;
  -moz-font-feature-settings: "liga" 1, "smcp" 1;
  -o-font-feature-settings: "liga" 1, "smcp" 1;
  -ms-font-feature-settings: "liga" 1, "smcp" 1;
}
```

## SCSS Output and Use
To use this boilerplate simply declare a class, use `@include font-feature-settings` to produce the OpenType CSS property and then pass in the values (OpenType features) you need. Each example shows the SCSS code on top followed by the preprocessed.

```scss
//One value
.className { @include font-feature-settings($liga); }

.className {
  font-feature-settings: "liga" 1;
  -webkit-font-feature-settings: "liga" 1;
  -moz-font-feature-settings: "liga" 1;
  -o-font-feature-settings: "liga" 1;
  -ms-font-feature-settings: "liga" 1;
}


//Two values
.differentClass { @include font-feature-settings($liga, $smcp); }

.differentClass {
  font-feature-settings: "liga" 1, "smcp" 1;
  -webkit-font-feature-settings: "liga" 1, "smcp" 1;
  -moz-font-feature-settings: "liga" 1, "smcp" 1;
  -o-font-feature-settings: "liga" 1, "smcp" 1;
  -ms-font-feature-settings: "liga" 1, "smcp" 1;
}
```

## Stylus Output and Use
To use this boilerplate simply declare a class, use `font-feature-settings` to produce the OpenType CSS property and then pass in the values (OpenType features) you need. Each example shows the Stylus code on top followed by the preprocessed.

```
//One value
.className
  font-feature-settings $liga

.className {
  font-feature-settings: "liga" 1;
  -webkit-font-feature-settings: "liga" 1;
  -moz-font-feature-settings: "liga" 1;
  -o-font-feature-settings: "liga" 1;
  -ms-font-feature-settings: "liga" 1;
}


//Two values
.differentClass
  font-feature-settings $liga, $smcp

.differentClass {
  font-feature-settings: "liga" 1, "smcp" 1;
  -webkit-font-feature-settings: "liga" 1, "smcp" 1;
  -moz-font-feature-settings: "liga" 1, "smcp" 1;
  -o-font-feature-settings: "liga" 1, "smcp" 1;
  -ms-font-feature-settings: "liga" 1, "smcp" 1;
}
```
