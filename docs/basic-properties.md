Basic Properties
================

This section covers the basic properties of generated popups.

ID
--
The `id` parameter sets the class name and localStorage
reference.

| Name | Type     | Default Value |
|------|----------|---------------|
| `id` | `string` | `popup`       |

The ID is useful to set if you plan on styling the popup with CSS
outside of the library - more information in [Custom Styles](popup-styling#custom-styles).

The popup ID is also used as a key for localStorage if you set the
popup to only show once - more information in [Show Once](popup-settings#show-once).

Having multiple popups with the same ID will cause issues, so if
you're using multiple popups per page, make sure to give each
popup a different ID.

Omitting the ID should not cause issues if none of the above are
used, though it is still recommended to give your popups an ID,
for example your [popup title](basic-properties#title) in [kebab-case](https://en.wikipedia.org/wiki/Letter_case#Kebab_case).


Title
-----
The `title` parameter sets the title of the popup shown.

| Name    | Type     | Default Value |
|---------|----------|---------------|
| `title` | `string` | `Popup Title` |

This paramater is the heading for your project/popup, so it should
ideally be short but descriptive. Omitting the title is not
recommended.


Content
-------
The `content` parameter sets the main description of the popup shown.

| Name      | Type     | Default Value   |
|-----------|----------|-----------------|
| `content` | `string` | `Popup Content` |

This library comes with a lot of ways to customize the popup content
without using CSS, which is expanded upon in [Styling](styling).

Width Multiplier
-----------
The `widthMultiplier` parameter sets the relative width of the popup.

| Name              | Type    | Default Value |
|-------------------|---------|---------------|
| `widthMultiplier` | `float` | `1`           |

By default, a popup is 770px wide unless that covers more than 80% of the screen width,
in which case the popup width is set to 80% of the screen width. The final width
equates to the default width times the width multiplier, so a value of 0.8 would
cover 616px or at maximum 64% of the screen width.

Height Multiplier
-----------
The `heightMultiplier` parameter sets the relative height of the popup.

| Name               | Type    | Default Value |
|--------------------|---------|---------------|
| `heightMultiplier` | `float` | `0.66`        |

The height formula is identical to the height formula, except the default value
already multiplies the calculated width by 0.66 so that the proportions are the
same on all screen widths and heights. A height multiplier of 0.8 would therefore
increase the height.

!!! note

    The library currently does not support setting the width or height to a fixed
    value in order to maintain responsiveness. You could, however, override it
    using [Overriding Styles](popup-styling#overriding-styles).

