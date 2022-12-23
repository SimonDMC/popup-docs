# Popup Settings

## Fixed Height

The `fixedHeight` parameter controls whether or not
the popup height is fixed.

| Name          | Type      | Default Value |
| ------------- | --------- | ------------- |
| `fixedHeight` | `boolean` | `false`       |

By default, the popup height is relative to its content.
Setting this parameter to true will make the popup height
fixed. The fixed height is calculated using the
[height formula](../basic-properties#height-multiplier).

## Show Immediately

The `showImmediately` parameter makes the popup appear
immediately on page load with no fade in animation.

| Name              | Type      | Default Value |
| ----------------- | --------- | ------------- |
| `showImmediately` | `boolean` | `false`       |

This parameter is best used in conjunction with [Show Once](#show-once)
to create an infographic for the first time the user visits the page.

## Show Once

The `showOnce` parameter only makes the popup appear once per
user.

| Name       | Type      | Default Value |
| ---------- | --------- | ------------- |
| `showOnce` | `boolean` | `false`       |

The check is only ran with the [Show Immediately](#show-immediately)
call, so any subsequent show method calls will still work.

!!! note

    The visibility only updates when the user closes the popup,
    so reloading the page before closing the popup will still
    display it.

## Allow Close

The `allowClose` parameter controls whether or not
the user can close the popup.

| Name         | Type      | Default Value |
| ------------ | --------- | ------------- |
| `allowClose` | `boolean` | `true`        |

If you're using the popup as a prompt and awaiting the user's
decision, not letting the user close the popup might be useful.
The popup can still be closed using the [.hide() method](../usage#closing-a-popup),
so this lets you control when exactly the popup goes away.

!!! note

    When using `allowClose`, you don't need to use the
    [Hide Close Button](#hide-close-button) parameter.

## Hide Close Button

The `hideCloseButton` parameter controls whether or not
the popup displays without a close button.

| Name              | Type      | Default Value |
| ----------------- | --------- | ------------- |
| `hideCloseButton` | `boolean` | `false`       |

When using the [Allow Close](#allow-close) parameter, you don't
need to use this parameter, as the close button is hidden
automatically.

Setting this parameter to true will hide the close button
but will still allow the user to close the popup by clicking
outside of it.

## Hide Title

The `hideTitle` parameter controls whether or not
the popup displays without a title.

| Name        | Type      | Default Value |
| ----------- | --------- | ------------- |
| `hideTitle` | `boolean` | `false`       |

## Disable Scroll

The `disableScroll` parameter controls whether or not
the user can scroll on the page while the popup is open.

| Name            | Type      | Default Value |
| --------------- | --------- | ------------- |
| `disableScroll` | `boolean` | `true`        |

By default, scrolling gets disabled when the popup is open
and reenables when the popup is closed. Setting this parameter
to false will allow the user to scroll behind the popup while
it's open.
