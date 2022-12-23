# Usage

## Installation

Install `popup-js` with the following script tag.

```html
<script src="https://cdn.jsdelivr.net/npm/@simondmc/popup-js@1.4.0/popup.min.js"></script>
```

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

## Load Callback

You can add a callback function to be called when the popup and all its
contents are first loaded with the `loadCallback` parameter.

Example:

```js
new Popup({
    loadCallback: () => {
        console.log("Popup loaded!");
    },
});
```

This is useful for, for example, adding event listeners to the popup's
elements.

Example:

```js
new Popup({
    content: `
        {btn-popup-button}[Click me!]`,
    loadCallback: () => {
        const button = document.querySelector(".popup-button");
        button.addEventListener("click", () => {
            console.log("Button clicked!");
        });
    },
});
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
