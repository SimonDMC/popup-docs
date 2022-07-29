Usage
=====

Installation
------------

Install `popup-js` using a script tag.

```html
  <script src="https://cdn.jsdelivr.net/npm/@simondmc/popup-js@1.1.1/popup.min.js"></script>
```
using npm or
```html
  <script src="https://cdn.jsdelivr.net/gh/SimonDMC/popup-js@1.1.1/popup.min.js"></script>
```
using github.

Creating a popup
----------------

Create a popup by instantiating the Popup class with customization parameters.

```javascript
const myPopup = new Popup({
    id: 'my-popup',
    title: 'My First Popup',
    content: `
        An example popup.
        Supports multiple lines.`
});
```

Though not recommended, you can also create a popup leaving the parameters empty, using all the default values.

```javascript
const myPopup = new Popup({});
```

With the way the library works, no paramaters are required, as they all have their default values, and
you won't need to use *most* of them *most* of the time, so changing only a few values should be
enough in *most* cases.

Displaying the popup
--------------------

Generated popups will not show up by default (unless created with the [Show Once parameter](../popup-settings#show-once)),
to make them appear, call the `.show()` method.

```javascript
const myPopup = new Popup({
  ...
});

myPopup.show();
```

!!! note

    If you want to display the popup on page load, use the [Show Once parameter](../popup-settings#show-once)
    instead as it has no fade in and is optimized for loading as soon as
    all the necessary files have downloaded.

Closing a popup
---------------
You can force close an open popup by calling the `.hide()` method.

Example:
```javascript
const myPopup = new Popup({
  ...
});

myPopup.show();
// keep popup open for 2 seconds
await sleep(2000);
myPopup.hide();
```