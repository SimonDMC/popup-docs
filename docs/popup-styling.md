Popup Styling
=============

This section covers the concepts of popup styling.

Background Color
----------------
The `backgroundColor` parameter sets the (background) color of the popup.

| Name              | Type    | Default Value |
|-------------------|---------|---------------|
| `backgroundColor` | `color` | `#ffffff`     |

Title Color
-----------
The `titleColor` parameter sets the color of the popup title.

| Name         | Type    | Default Value |
|--------------|---------|---------------|
| `titleColor` | `color` | `#000000`     |

Text Color
----------
The `textColor` parameter sets the color of the popup content text.

| Name        | Type    | Default Value |
|-------------|---------|---------------|
| `textColor` | `color` | `#000000`     |

Close Color
-----------
The `closeColor` parameter sets the color of the popup close button.

| Name         | Type    | Default Value |
|--------------|---------|---------------|
| `closeColor` | `color` | `#000000`     |

Link Color
----------
The `closeColor` parameter sets the color of links within the popup body.

| Name        | Type    | Default Value |
|-------------|---------|---------------|
| `linkColor` | `color` | `#383838`     |

Side Margin
-----------
The `sideMargin` parameter sets the inner margin on the popup content sides.

| Name         | Type     | Default Value |
|--------------|----------|---------------|
| `sideMargin` | `length` | `3%`          |

The larger the value, the more lines the popup content will be split into.

Title Margin
------------
The `titleMargin` parameter sets the bottom margin of the popup title, which 
renders as the distance between the popup title and content.

| Name          | Type     | Default Value |
|---------------|----------|---------------|
| `titleMargin` | `length` | `2%`          |

Line Spacing
------------
The `lineSpacing` parameter sets the spacing between popup content lines.

| Name          | Type     | Default Value |
|---------------|----------|---------------|
| `lineSpacing` | `length` | `auto`        |

Button Width
------------
The `buttonWidth` parameter sets the width of all buttons within the popup 
content.

| Name          | Type     | Default Value |
|---------------|----------|---------------|
| `buttonWidth` | `length` | `fit-content` |

!!! note

    This may seem, and usually is, useless, but it has its specific use case - 
    having a consistent button width is useful when dealing with multiple left 
    or right aligned buttons.

Custom Styles
-------------

If you want to style a specific part of a popup outside of the realm
of the built-in properties, you can do so via an external stylesheet.

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
define the following CSS rule in a stylesheet.

```css
/* optional .popup */ .popup-header {
    font-weight: bold;
}
```

If you are using multiple popups on the same page, you can use the [popup ID](../basic-properties#id)
to distinguish between individual popups. Applying the above example to a popup
with an ID of `instructions` would look like such: 

```css
.popup.instructions .popup-header {
    font-weight: bold;
}
```

Overriding Styles
-----------------

You can also override pre-defined popup styles using the CSS `!important` tag.
For example, removing the rounded corners from all popups would be done using 
the following CSS code snippet.

```css
/* optional .popup */ .popup-content {
    border-radius: 0 !important;
}
```

The above rules also apply to specific popup styling.