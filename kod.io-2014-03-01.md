[The Chroma Zone - Engineering Color on the Web](http://leaverou.github.io/chroma-zone)
==============================================

by [Lea Verou](https://twitter.com/LeaVerou)

* open source projects
  * prismjs.com
  * -prefix-free
  * css3test.com
* member of css working group, prev. member of w3c

how color works on the screen
-----------------------------

* white pixels made up of 3 subpixels (rgb)
  * can have different order
  * different subpixel intensities for different colors

rgb
---

* can be thought of as a coordinate system
  * can be mapped to a cube
  * most color pickers flatten one of the dimensions and then allow you to tweak the other two
* in css, we can set colors with the rgba() notation or #xxxxxx / #xxx hex notation
  * both forms are confusing
* another option: css color names
  * very ugly colors
  * some newer: super long, racist, or completely crazy (dark gray )
* currentColor in css3
* fun rgb / hsl guessing game: [http://leaverou.github.io/whatthecolor](http://leaverou.github.io/whatthecolor)

hsl
---

* different coord system: can be mapped to a cone
* lightness in hsl is not perceptual lightness for us as humans, because it's just a transformation of rgb
  * lightness is not the same as luminance

enter: relative luminance
-------------------------

* from wcag 2.0, css4
* to achieve perceptual lightness, blue is multiplied by smaller number as green as red

alpha blending
--------------

* compositing two colors and alpha strengths to calculate what the opaque color should be

css4
----

* gray(xx%) - unsupported now, but can be polyfilled with sass
* adjustors: tint, shade, blend


[AngularJS and i18n](http://pascalprecht.github.io/slides/angularjs-and-i18n/#/)
===================

by [Pascal Precht](https://twitter.com/PascalPrecht)

* professional animated gif executer

angularjs
---------

* design as if html had been designed for apps (html++ so to say)
* two way data binding
  * one single source of truth (within scopes)
  * declarative views, don't need to write traditional javascript code
* directives to define functionality on elements
* web components to define your own elements
* routes
* built with testability in mind

internationalization / localization
-----------------------------------

* abstracting your strings for use in different languages, countries
* angular support
  * datetime, number, currency, ngPluralize
  * $locale service (from ngLocale)
  * unfortunately, that's it - can't translate all strings

introducing angular-translate
-----------------------------

* typical components: services, filters, directives
* var replacement
* multi-language
* fallback languages
* missing tranlsation support
* async
* localStorage to save locale
* changing the language at runtime with simple controller method

How to Get More Women in Tech in 5 Steps
========================================

by [Anika Lindtner](https://twitter.com/langziehohr)

* Travis CI supporter of Railsgirls from the start
* very low population of women in
* traditional answers
  * "they're just not so good at it"
  * "they're just not interested"
  * we know that these are not true
* stereotypes are much different today than earlier
* there are no gender-specific abilities
* missing role models
* fear of change

Where can we start?
-------------------

* daily life - talking, why you love what you do
* support and inspire others