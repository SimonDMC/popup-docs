Usage
=====

Installation
------------

Install `popup-js` using a script tag.

```html
  [TODO] <script src="https://cdn.jsdelivr.net/npm/popup-js@latest/popup.min.js"></script>
```
through npm or
```html
  [TODO] <script src="https://cdn.jsdelivr.net/gh/SimonDMC/popup-js/src/popup.min.js"></script>
```
through github.

Creating a popup
----------------

Create a popup by instantiating the Popup class with customization parameters.

```javascript
const my-popup = new Popup({
    id: 'my-popup',
    title: 'My First Popup',
    content: `
        An example popup.
        Supports multiple lines.`
});
```

Though not recommended, you can also create a popup leaving the parameters empty, using all the default values.

```javascript
const my-popup = new Popup({});
```

With the way the library works, no paramaters are required, as they all have their default values, and
you won't need to use *most* of them *most* of the time, so changing only a few values should be
enough in *most* cases.