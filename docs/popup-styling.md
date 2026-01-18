# Popup Styling

This section covers the concepts of popup styling.

## Background Color

The `backgroundColor` parameter sets the (background) color of the popup.

| Name              | Type    | Default Value |
| ----------------- | ------- | ------------- |
| `backgroundColor` | `color` | `#ffffff`     |

## Title Color

The `titleColor` parameter sets the color of the popup title.

| Name         | Type    | Default Value |
| ------------ | ------- | ------------- |
| `titleColor` | `color` | `#000000`     |

## Text Color

The `textColor` parameter sets the color of the popup content text.

| Name        | Type    | Default Value |
| ----------- | ------- | ------------- |
| `textColor` | `color` | `#000000`     |

## Close Color

The `closeColor` parameter sets the color of the popup close button.

| Name         | Type    | Default Value |
| ------------ | ------- | ------------- |
| `closeColor` | `color` | `#000000`     |

## Link Color

The `linkColor` parameter sets the color of links within the popup body.

| Name        | Type    | Default Value |
| ----------- | ------- | ------------- |
| `linkColor` | `color` | `#383838`     |

## Underline Links

The `underlineLinks` parameter sets whether links within the popup body are underlined.

| Name             | Type      | Default Value |
| ---------------- | --------- | ------------- |
| `underlineLinks` | `boolean` | `false`       |

## Border Radius

The `borderRadius` parameter controls how rounded the popup content
corners are.

| Name           | Type     | Default Value |
| -------------- | -------- | ------------- |
| `borderRadius` | `length` | `15px`        |

## Border Width

The `borderWidth` parameter controls the width of the popup border.
By default, the border is set to 0px, which means that the popup will
not have a border.

| Name          | Type     | Default Value |
| ------------- | -------- | ------------- |
| `borderWidth` | `length` | `0px`         |

## Border Color

The `borderColor` parameter controls the color of the popup border.

| Name          | Type    | Default Value |
| ------------- | ------- | ------------- |
| `borderColor` | `color` | `#000000`     |

## Side Margin

The `sideMargin` parameter sets the inner margin on the popup content sides.

| Name         | Type     | Default Value |
| ------------ | -------- | ------------- |
| `sideMargin` | `length` | `3%`          |

The larger the value, the more lines the popup content will be split into.

## Title Margin

The `titleMargin` parameter sets the bottom margin of the popup title, which
renders as the distance between the popup title and content.

| Name          | Type     | Default Value |
| ------------- | -------- | ------------- |
| `titleMargin` | `length` | `2%`          |

## Line Spacing

The `lineSpacing` parameter sets the spacing between popup content lines.

| Name          | Type     | Default Value |
| ------------- | -------- | ------------- |
| `lineSpacing` | `length` | `auto`        |

## Button Width

The `buttonWidth` parameter sets the width of all buttons within the popup
content.

| Name          | Type     | Default Value |
| ------------- | -------- | ------------- |
| `buttonWidth` | `length` | `fit-content` |

!!! note

    This may seem, and usually is, useless, but it has its specific use case -
    having a consistent button width is useful when dealing with multiple left
    or right aligned buttons.

## Font

The `font` parameter sets the font family of the popup content.

| Name   | Type     | Default Value |
| ------ | -------- | ------------- |
| `font` | `string` | `Inter`       |

The default font is [Inter](https://rsms.me/inter/), which comes
pre-imported with the popup library. You can pass a web-safe font
family, or a font family that you have imported into your project.

The easiest way to import a font is to add an `@import` statement
to the top of the css parameter.

```js
new Popup({
    content: "This is in Roboto!",
    font: "Roboto",
    css: `@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');`,
});
```

If the passed font is not found, the popup font will fall back to
Inter.

## Text Shadow

The `textShadow` parameter sets the text shadow of the popup.

| Name         | Type     | Default Value |
| ------------ | -------- | ------------- |
| `textShadow` | `string` | `none`        |

This parameter accepts a string in the format of the
[CSS text-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow)
property.

Keep in mind the text shadow applies to the entire popup, not just
the content. This means that the title and close button will also
be affected by the text shadow.

## Custom Styles

If you want to style a specific part of a popup outside of the realm
of the built-in properties, you can do so via the `css` parameter.

The selector for any popup is `.popup`, the hierarchy then goes as such:

```

.popup
└ .popup-content
└ .popup-header
└ .popup-title
└ Title
└ .popup-close
└ Close Button
└ .popup-body
└ Content

```

For example, if you wanted to make the header text bold, you could
pass the following CSS code snippet to the `css` parameter.

```js
new Popup({
    ...
    css: `
        /* optional .popup */
        .popup-header {
            font-weight: bold;
        }`
});
```

If you are using multiple popups on the same page, you can use the [popup ID](../basic-properties#id)
to distinguish between individual popups. Applying the above example to a popup
with an ID of `instructions` would look like such:

```js
new Popup({
    ...
    css: `
        .popup.instructions .popup-header {
            font-weight: bold;
        }`
});
```

## Overriding Styles

You can also override pre-defined popup styles using the CSS `!important` tag.
For example, changing the background color of all popups to red would look like
this:

```js
new Popup({
    ...
    css: `
        .popup {
            background-color: red !important;
        }`
});
```

The above rules also apply to specific popup styling.

!!! note

    When targeting a specific popup, using the `!important` tag is
    often not necessary, as the popup ID will override the default
    styling.
