---
PG_TITLE: Web GPU
---

# Web GPU

## Introduction
As you might be aware, the next gen Web 3D is starting to rise.

Following the specification from the [W3C group](https://github.com/gpuweb/gpuweb), we have started our journey to support this new tech. Our plan is to deliver a support with WebGL feature parity and  the new WebGPU specifics in 4.1.

![Inspector](/img/extensions/WebGPU.png)

## Why ?
The promise behind WebGPU is an awesomely faster API providing lower level control to the graphic resources from Javascript. We hope to bring those extra performances to you in order to create even bigger Web 3D experiences through an API you are already familiar with: Babylon.js.

Also this is brigging new cool toys to the table like Compute Shaders and more to come.

## Where are we ?

We currently only support a really small subsets of what Babylon.js can do:
* Static Meshes and instances (no bones or morph)
* Basic PBR Materials (only IBL, albedo, specular, roughness, ambient and emissive data, can not change after creation)
* No other materials so far
* GLTF/GLB loader for model respecting the following limitations
* No custom effects or post processes
* No render targets

This is not much you would say, but it means we have layered all the ground foundation to move forward :-)

## How ?
The current implementation status is fully available on [Github](https://github.com/BabylonJS/Babylon.js/tree/WebGPU).

We will put a big effort all along our next release to implement the support and every contribution is more than welcome; So feel free to create some PR if you are interested in contributing to a fresh engine implementation based on cutting edge tech.

## What could go wrong ?
As this is really early in the development, we are subject to a lot of potential changes as well as spec uncertainties. We will deal with them one at a time but we may be subject to change the release schedule at any time.

We have the full support from the amazing teams implementing the browsers support so it will be easier to directly chat with them when needed.

## What would the migration look like for my app ?
As back compat is one of our pillar, the only difference we wish to have is the engine initialization which needs to be asynchronous:

```javascript
const engine = new BABYLON.WebGPUEngine(canvas);
await engine.initEngineAsync();
```

## Will WebGL still be supported ?
FOR SURE :-) There is no change of plans and we will deliver both supports side by side.

## I want to test it
You can only at the moment build your own version of Chrome to develop locally. Once there will be easier solutions, we won't hesitate to update this page.

You can follow the status from the dedicated [Chrome Status Platform Page](https://www.chromestatus.com/feature/6213121689518080).

Here is a link to a simple PBR sphere [Sphere](https://www.babylonjs.com/demos/WebGPU/oneSphereWebGPU.html)

And one to the famous [Damaged Helmet Demo](https://www.babylonjs.com/demos/WebGPU/oneHelmetWebGPU.html)