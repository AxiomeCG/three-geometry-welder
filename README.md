<div align="center">
	<br>
	<h1>three-geometry-welder</h1>
	<p>
		<b>A customizable way of merging your buffer geometry</b>
	</p>
</div>
<br>

# Stack 🧰

<p>
    <img src="https://img.shields.io/badge/threejs-black?style=for-the-badge&logo=three.js&logoColor=white" alt="ThreeJS Badge">
    <img src="https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white" alt="Typescript Badge">
</p>

- Threejs (r145)
- @types/three (r144)

# Quick Start 🏁

➡️[ Documentation ](https://0xaxiome.github.io/docs/three-geometry-welder/v0.1.0/)⬅️

## How to use this library 🔧

Run `npm install three-geometry-welder`

Then you can use in your code:

```typescript
import { BufferGeometryWelder } from "three-geometry-welder";

//...

const geometry = this.myMesh.geometry;

const geometryWelder = new BufferGeometryWelder(geometry, false, 6); // The second and third parameter are optional.
const destinationGeometry = geometryWelder.getMergedBufferGeometry();

const myIndexedMesh = new Mesh(destinationGeometry, this.myMesh.material);
this.myMesh.geometry.dispose(); //If you want to get rid of your old geometry not indexed.
this.myMesh = myIndexedMesh;
```


# Special Thanks 💖

This code is a reworked one in typescript of `toIndexed()` method of [@Fyrestar](https://github.com/Fyrestar)
that you can find [here](https://github.com/Fyrestar/THREE.BufferGeometry-toIndexed).

The code was hard to use in my Typescript project, I reworked, cleaned and made a service of it, to be easier to use. 

The code was left unmaintained, but it is really useful and works better than mergeVertices(). 

# Features 🛠️

- Enables to get an indexed geometry from a non indexed one.
- Can be on full set of attributes or only on the position attribute.
- The precision parameter enables you to simplify your geometry which can increase the performance of your app (with a tradeoff on the mesh accuracy: with a very low precision value, you will get a very low-poly mesh)

# Notes 🗒️

**How is it different from mergeVertices() from the official ThreeJS library?:**

It is meant to do the same job. I encountered a lot of problems with mergeVertices() and there is a lack of customization.
For example, I tried to use mergeVertices() of a 3D scan, it was unsuccessful to do so, and also making all in the mesh. 

Here you can also change the behaviour of the welder if you don't want it to check the full set of attributes.

# Twitter 🐦

You can reach me on Twitter:

[![Twitter](https://img.shields.io/badge/Twitter-%231DA1F2.svg?style=for-the-badge&logo=Twitter&logoColor=white)](https://twitter.com/0xAxiome)
