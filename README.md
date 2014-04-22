Event plugin
===========

Declaratively add event listeners to your views. It can also delegate events to a parent element. It's a plugin for [Seam](https://github.com/flams/seam).

Installation
============

```bash
npm install event-plugin
```

How to use
==========

Require event-plugin:

```js
var EventPlugin = require("event-plugin");
```

Init event plugin and define event handlers:

```js
var eventPlugin = new EventPlugin({
    toggle: function (event, node) {
        // do something with...
        // event is the original event
        // node is the dom node that was clicked
    }
});
```

```html
<!-- The toggle function will be called on click, on the propagation phase -->
<button data-event="listen: click, toggle, true">Change route</button>
```

When ready, attach the behavior to the dom via Seam:

```js
var Seam = require("seam");

var seam = new Seam();

seam.addAll({
    event: eventPlugin
});

seam.apply(document.querySelector("button"));
```



LICENSE
=======

MIT
