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

Allow Close
-----------

The `allowClose` parameter controls whether or not
the user can close the popup.

| Name         | Type      | Default Value |
|--------------|-----------|---------------|
| `allowClose` | `boolean` | `true`        |

If you're using the popup as a prompt and awaiting the user's
decision, not letting the user close the popup might be useful.
The popup can still be closed using the [.hide() method](../usage#closing-a-popup),
so this lets you control when exactly the popup goes away.