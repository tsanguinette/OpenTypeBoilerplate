# Type Quest 2.0
After many years of neglect, the original Type Quest is finally getting an update between late 2017 and early 2018. Stay tuned for the release! In the meantime, you can continue to use the old site found at the link below.

If you have any suggestions for the project, please contact me at [http://tylersanguinette.com/#contact-me](http://tylersanguinette.com/#contact-me).

# OpenType Mixin Boilerplate
A preprocessor boilerplate to easily use webfont OpenType features with CSS. This Git is an addition to a thesis project which promotes and educates webfont OpenType features through the W3C lower-level `font-feature-settings` CSS property.

* Author: Tyler Sanguinette 2013-2014
* Contributors: Jorge Colindres 2014; Michael Russell 2014
* License: MIT

**Thesis Project:** [http://tylersanguinette.com/typequest/](http://tylersanguinette.com/typequest/)
**Thesis Presentation:** [http://tylersanguinette.com/typequest/presentation](http://tylersanguinette.com/typequest/presentation)

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
@rlig: "rlig" 1; //Required Ligatures
@smcp: "smcp" 1; //Small Caps
@c2sc: "c2sc" 1; //Small Caps from Caps
@unic: "unic" 1; //Unicase
@cpsp: "cpsp" 1; //Capital Spacing
@aalt: "aalt" 1; //Access All Alternates
@titl: "titl" 1; //Titling Alternates
@lnum: "lnum" 1; //Lining Numbers
@onum: "onum" 1; //Old-style Numbers
@ordn: "ordn" 1; //Ordinals
@sups: "sups" 1; //Superscript
@subs: "subs" 1; //Subscript
@sinf: "sinf" 1; //Scientific inferiors
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
@pcap: "pcap" 1; //Petite Capitals
@ss01: "ss01" 1; //Stylistic Set 1
@ss02: "ss02" 1; //Stylistic Set 2
@ss03: "ss03" 1; //Stylistic Set 3
@ss04: "ss04" 1; //Stylistic Set 4
@ss05: "ss05" 1; //Stylistic Set 5
@ss04: "ss06" 1; //Stylistic Set 6
@size: "size" 1; //Optical Size
@locl: "locl" 1; //Localized Forms
@zero: "zero" 1; //Slashed Zero
@case: "case" 1; //Case Sensitive Forms
@mgrk: "mgrk" 1; //Mathematical Greek
@nalt: "nalt" 1; //Alternate Annotation Forms
@ornm: "ornum" 1; //Ornaments

//Language Support
@isol: "isol" 1; //Isolated Forms
@init: "init" 1; //Initial Forms
@medi: "medi" 1; //Medial Forms
@fina: "fina" 1; //Final Forms
@ccmp: "ccmp" 1; //Glyph Composition/Decomposition
@mark: "mark" 1; //Mark to Base Positioning
@mkmk: "mkmk" 1; //Mark to Mark Positioning

@akhn: "akhn" 1; //Akhands
@vatu: "vatu" 1; //Vettu Variants
@pkna: "pkna" 1; //Proportional Kana
```

## LESS Markup pattern
Use values from the variable section. Note the difference between LESS, SCSS and stylus multiple values.

```less
h1{
  .font-feature-settings(@value);
}

h1{
  .font-feature-settings(@value, @value1;);
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
  .font-feature-settings(@liga, @smcp;);
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
