# `<silicon-image>`
Displays a rasterized binary image with `silicon-image-behavior`.  You need to provide your own containing block, as the element has `absolute` positioning so that other images can be stacked.

I suggest something like this if you've got it wrapped in a `<div>`, which itself is in a flexbox:

```css
div {
  flex: 1 1 0;
  width: 412px; <you can change this dynamically>
  overflow-y: scroll;
  position: relative;
  background-color: grey;
  margin-bottom: 8px;
}
```

or something like this div, if no flexbox:

```css
div {
  overflow-y: scroll;
  height: 200px;
  width: 412px;
  position: absolute;
  background-color: grey;
}
```

Example:

```html
<silicon-image size="[[size]]" width="400" style="z-index: 10;" zoom="10" offset="{{offset}}"></silicon-image>
```

As the mouse moves over the image, `offset` is updated, so listen for an `offset-changed` event, or two-way data-bind to `offset` if you're using Polymer.

See the [documentation](http://m4b.github.io/silicon-image) for more information.

# Install

Via bower:

`bower install silicon-image`

As with all Silicon Elements, this requires Polymer, and the webcomponents polyfill (for now).

Example:

```html
<head>
<script src="bower_components/webcomponentsjs/webcomponents-lite.js"></script>
<link rel="import" href="bower_components/polymer/polymer.html">
<link rel="import" href="bower_components/silicon-image/silicon-image.html">
</head>
```
