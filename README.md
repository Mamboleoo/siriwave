# SiriWave

The "Apple Siri" wave replicated in pure Javascript using the Canvas API.

[Read blog post here](https://developers.caffeina.com/how-i-built-siriwavejs-library-maths-and-code-behind-6971497ae5c1)

[Demo](http://kopiro.github.io/siriwave)

[![npm version](https://badge.fury.io/js/siriwave.svg)](https://badge.fury.io/js/siriwave)

### Classic style

<img src="etc/classic.gif" />

### iOS 9+ style

<img src="etc/ios9.gif" />

## Usage

### Browser (via CDN) usage

```html
<script src="https://unpkg.com/siriwave/dist/siriwave.umd.min.js"></script>
```

### ES module

Install it through `npm install siriwave` or `yarn add siriwave` first:

```js
import SiriWave from "siriwave";
```

## Init

Create a div container and instantiate a SiriWave object

```html
<div id="siri-container"></div>
<script>
  var siriWave = new SiriWave({
    container: document.getElementById("siri-container"),
    width: 640,
    height: 200,
  });
</script>
```

## Constructor options

| Key             | Type               | Description                                                            | Default    | Required |
| --------------- | ------------------ | ---------------------------------------------------------------------- | ---------- | -------- |
| container       | DOMElement         | The DOM container where the DOM canvas element will be added.          | null       | yes      |
| style           | "ios", "ios9"      | The style of the wave.                                                 | "ios"      | no       |
| ratio           | Number             | Ratio of the display to use. Calculated by default.                    | calculated | no       |
| speed           | Number             | The speed of the animation.                                            | 0.2        | no       |
| amplitude       | Number             | The amplitude of the complete wave-form.                               | 1          | no       |
| frequency       | Number             | The frequency of the complete wave-form. Only available in style "ios" | 6          | no       |
| color           | String             | Color of the wave. Only available in style "ios"                       | "#fff"     | no       |
| cover           | Bool               | The `canvas` covers the entire width or height of the container        | false      | no       |
| autostart       | Bool               | Decide wether start the animation on boot.                             | false      | no       |
| pixelDepth      | Number             | Number of step (in pixels) used when drawed on canvas.                 | 0.02       | no       |
| lerpSpeed       | Number             | Lerp speed to interpolate properties.                                  | 0.01       | no       |
| curveDefinition | ICurveDefinition[] | Override definition of the curves                                      | null       | no       |

## API

#### `start()`

Start the animation

#### `stop()`

Stop the animation.

#### `setSpeed(newValue)`

Set the new value of speed (animated)

#### `setAmplitude(value)`

Set the new value of amplitude (animated)

#### `dispose()`

Stop the animation and destroy the canvas, by removing it from the DOM.
Subsequent `start()` calls on this SiriWave instance will fail with an exception.
## Grapher plots

- [GCX default](etc/gcx/default.gcx)
- [GCX iOS 9](etc/gcx/ios9.gcx)

## Build and development

If you wanna make some modifications in your local environment, use:

```
yarn dev
```

this will create a watchable build with RollupJS and automatically create a server to see your changes in the browser.

To finally build all targets:

```
yarn build
```

## QA

#### How do I integrate this library with a microphone user input?

You can find an excellent demo [here](https://jsitor.com/PPQtOp9Yp) by @semmel
