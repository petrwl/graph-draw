# graph-draw
A JavaScript library for tessellating undirected planar graphs for Node and browsers.
It can be used to draw boundaries or polylines on a map.

[![screenshot](/docs/img/intro.png)](https://manubb.github.io/graph-draw/basic-demo.html)

## Demo

A very basic [demo](https://manubb.github.io/graph-draw/basic-demo.html).

# Installation
graph-draw is available as a npm package:
```
npm install graph-draw
```
In Node:
```js
var graphDraw = require('graph-draw');
```

In browsers, include one file from the dist directory. (Files with name that contains "bundle" include libtess.)

# Usage
```js
var vertices = [[0, 0], [100, 0], [100, 100], [0, 100]];
// coordinates of the vertices

var edges = [[0, 1], [1, 2], [2, 3], [3, 0], [1, 3]];
// each edge is specified with the indices of the linked vertices
// each edge must appear exactly once in the list
// ([0, 1] and [1, 0] are the same edges)

var graph = {vertices: vertices, edges: edges};
var strokeWidth = 10;
var triangles = graphDraw(graph, strokeWidth);
```
A list of triangles is returned:
```js
[
  [ [ -5, -5 ], [ 87.92893218813452, 5 ], [ 5, 5 ] ],
  [ [ 87.92893218813452, 5 ], [ -5, -5 ], [ 105, -5 ] ],
  ...
]
```
