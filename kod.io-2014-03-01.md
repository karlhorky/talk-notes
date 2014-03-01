The Chroma Zone - Engineering Color on the Web
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
* fun rgb / hsl guessing game: [http://leaverou.github.io/whatthecolor](http://leaverou.github.io/whatthecolor)

enter: the JS color class
-------------------------

*