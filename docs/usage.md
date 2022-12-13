# Usage

## Installation

Install `popup-js` using a script tag.

```html
<script src="https://cdn.jsdelivr.net/npm/@simondmc/popup-js@1.3.1/popup.min.js"></script>
```

using npm or

```html
<script src="https://cdn.jsdelivr.net/gh/SimonDMC/popup-js@1.3.1/popup.min.js"></script>
```

using github.

## Creating a popup

Create a popup by instantiating the Popup class with customization parameters.

```javascript
const myPopup = new Popup({
    id: "my-popup",
    title: "My First Popup",
    content: `
        An example popup.
        Supports multiple lines.`,
});
```

Though not recommended, you can also create a popup without any parameters, using all the default values.

```javascript
const myPopup = new Popup();
```

With the way the library works, no parameters are required, as they all have their default values, and
you won't need to use _most_ of them _most_ of the time, so changing only a few values should be
enough in _most_ cases.

## Displaying the popup

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

## Closing a popup

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

## Close Callback

You can add a callback function to be called when the popup is closed
with the `hideCallback` parameter.

Example:

```javascript
const myPopup = new Popup({
    hideCallback: () => {
        console.log("Popup closed!");
    },
});
```
