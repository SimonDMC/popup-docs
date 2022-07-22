Popup Settings
==============

Dynamic Height
--------------

The `dynamicHeight` parameter controls whether or not
the popup height is fixed.

| Name            | Type      | Default Value |
|-----------------|-----------|---------------|
| `dynamicHeight` | `boolean` | `false`       |

By default, the popup height is calculated using a [height formula](../basic-properties#height-multiplier).
Setting the dynamic height parameter to true overrides the formula and
instead sets the popup height to its contents (plus some extra margin).

Show Immediately
--------------

The `showImmediately` parameter makes the popup appear
immediately on page load with no fade in animation.

| Name              | Type      | Default Value |
|-------------------|-----------|---------------|
| `showImmediately` | `boolean` | `false`       |

This parameter is best used in conjunction with [Show Once](#show-once)
to create an infographic for the first time the user visits the page.

Show Once
---------

The `showOnce` parameter only makes the popup appear once per
user.

| Name       | Type      | Default Value |
|------------|-----------|---------------|
| `showOnce` | `boolean` | `false`       |

The check is only ran with the [Show Immediately](#show-immediately)
call, so any subsequent show method calls will still work.

!!! note

    The visibility only updates when the user closes the popup,
    so reloading the page before closing the popup will still
    display it.

