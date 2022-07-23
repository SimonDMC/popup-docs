Content Styling
===============

**popup-js** provides numerous quality of life features
to make writing popup content as simple as possible.

Reduced Element Formatting
--------------------------
If you want to include a link in your popup content, you
can do so using the `{a-<href>}[<display text>]` syntax.

Example:
```javascript
...
content: `
    Click {a-https://example.com}[here] to learn more.
`,
...
```

A button can be defined using the `{btn-<class>}[<display text>]` syntax.

Example:
```javascript
...
content: `
    Reset Progress     {btn-reset}[Reset]
`,
...
```

Non-breaking Spaces
-------------------
If you want a gap within a content line, simply using
multiple consecutive spaces will do the trick, as they
automatically get converted to non-breaking spaces if
necessary.

Example:
```javascript
...
content: `
    This sentence           has a large gap.
`,
...
```

Line properties
---------------
The library also provides useful methods for styling
and entire line.

A line with a larger upper margin would be defined using
the `big-margin§<text>` syntax.

Example: 
```javascript
...
content: `
    This line has the default margin.
    big-margin§This line has a larger margin than usual.
    This line also has the default margin.
`,
...
```

You can also make elements within the line align left and right
respectively, for example for a settings popup, using the 
`space-out§<element 1><element 2>` syntax.

The elements can be text and a button, two buttons, or anything
else, however bear in mind you will have to isolate the text
in a `<span>` element if you want both elements to be text.

A practical example is shown below, along with an image of how
such popup content would look.

```javascript
...
content: `
    space-out§Color Scheme{btn-colorSchemeButton}[Toggle]
    space-out§Clear Storage{btn-clearStorageButton red-button}[Clear]
`,
...
```
![Space Out content style showcase](https://media.discordapp.net/attachments/847794209028833310/1000333531278475304/unknown.png)

Text Styling
------------
The library also provides a handful of text styling
options. All of these are applied using the `{<properties>}[<text>]` syntax.

Here is a complete list of provided styles:
```
white
black
red
green
blue
bold
shadow
```

Examples:
```javascript
...
content: `
    {red}[This text is red.]
`,
...
```

```javascript
...
content: `
    The word {white bold shadow}[banana] is white, bold, and has a shadow.
`,
...
```

Button Styling
--------------
There is also basic button coloring support available, with the 
[Reduced Element Formatting](#reduced-element-formatting) syntax,
where the button style is the class. The options are `red-button`, 
`green-button` and `blue-button`.

Example:
```javascript
...
content: `
    This is a {btn-blue-button}[Blue Button].
`,
...
```

Custom Styles
-------------
You can add custom styles to parts of the popup content using the
[Text Styling](#text-styling) syntax, with a selector as the style
property which you can then use in an external style sheet.

Consider the following example:
```javascript
...
content: `
    This part of the text will have {custom-style}[custom styling].
`,
...
```
Adding a custom style to the isolated part of the content is as simple as:
```css
.custom-style {
    /* whatever custom styles */
    font-variant: small-caps;
}
```
Find out more about popup selector hierarchy in [Custom Popup Styles](../popup-styling#custom-styles).

To apply custom styles to an entire line, you can use the
[Line Properties](#line-properties) syntax with the same
CSS code as above.

Example:
```javascript
...
content: `
    custom-style§This entire line will have custom styling.
`,
...
```

To override default styles, use the method from [Overriding Popup Styles](../popup-styling#overriding-styles).