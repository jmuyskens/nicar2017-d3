
By John Muyskens ([@JohnMuyskens](twitter.com/johnmuyskens)) and Leslie Shapiro ([@lmshap](twitter.com/lmshap)). We are members of the Washington Post graphics team (@postgraphics) who specialize in data journalism.

[Slides](https://docs.google.com/presentation/d/1cAHnGb3YDaa3IHss3mP4a0gH_eDXY6BP-ous2bKY1BI/).

# Nesting
Goal is to structure your data the way you want your DOM to look.

A quick note on functional programming APIs in JavaScript:

Filter: separate the wheat from the chaff

Map: apply a function to an array, producing a new array. Remember to return! (also forEach)

Reduce: iterate over an array, producing a single value. If you just want to sum or do simple stats you can use d3.sum etc.

`Nest` is like "groupBy" in other functional programming languages

TK link to nest docs

![nest diagram](img/nest.png)

`.entries` returns an array

`.map` returns an object which is useful for creating lookup tables. There's also `.object` which you can use if you are sure your data doesn't collide with js reserved words. JS objects not equal to hash tables like python dicts but can be used in much the same way.

[Try it out!](http://bl.ocks.org/jmuyskens/raw/7afd1f9f2b6bd0b767b2df346d39a847/)


# Dates
TK link to date docs

`d3.dateParse` returns a function that turns a String into a Date

`d3.dateFormat` returns a function that turns a Date into a String

The format DSL is like strptime in other langs worth learning the most common args

[Try it out!](https://runkit.com/npm/d3-time-format)

# Scale options
TK link d3-scale docs

`d3.scaleLinear` may not be the most appropriate choice for our x axis. Let's try using `d3.scaleTime` instead.

- scaleTime
- scaleSqrt
- scaleLog
- scaleOrdinal

# Axis formatting options

`.tickSize` specify length of ticks

`.ticks` specify number of ticks, but d3 does some thinking for you (TK why)

The backbone of the axis is a <path> while the ticks are <line>s so you can easily style them separately.

Use `.attr('transform', 'translate(TK, TK)')` to move your axis around.

# Advanced nesting for multiple time series
You can keep adding layers to your nest by adding `.key`s. Our line function expects an array of arrays because the enter pattern expects an array and the line function also expects an array.

Note that there are missing values for some days, so a line chart may not be the most appropriate choice here.

# Scatterplot
We won't need to nest our data

Change y axis

Write new enter pattern for `<circle>`

# Interaction
.on
mouseenter
mouseleave
mouseover
touch?
how you would integrate tooltips
how to select this element

# Voronoi
Improve your scatter interaction
Visualize voronoi
Connect to circles

# Transitions
transition x axis

# what's in the advanced class
Layouts (force, heirarchy)
Geo tools
Modules
Behaviors (drag and zoom)
Canvas

# libraries and tools you may find useful
crowbar
jetpack
[d3-legend](http://d3-legend.susielu.com/)
[Textures.js](https://riccardoscalco.github.io/textures/)
swoopy drag

http://d3-legend.susielu.com/
