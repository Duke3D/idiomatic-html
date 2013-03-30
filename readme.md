# Principles of Writing Consistent, Idiomatic HTML

The following document outlines a reasonable style guide for HTML development.
These guidelines strongly encourage the use of existing, common, sensible
patterns. They should be adapted as needed to create your own style guide.

This is a living document and new ideas are always welcome. Please contribute.


## Table of Contents

1. [General Principles](#general-principles)
2. [Whitespace](#whitespace)
3. [Format](#format)
4. [Attribute Order](#attribute-order)
5. [Naming](#naming)
6. [Practical Example](#example)
7. [Afterword](#afterword)

[Acknowledgements](#acknowledgements) & [License](#license).


<a name="general-principles"></a>
## 1. General Principles

<blockquote>
“Part of being a good steward to a successful project is realizing that
writing code for yourself is a bad idea. If thousands of people are using
your code, then write your code for maximum clarity, not your personal
preference of how to get clever within the spec.” — Idan Gazit.
</blockquote>

<blockquote>
“Arguments over style are pointless. There should be a style guide,
and you should follow it.” — Rebecca Murphey.
</blockquote>

<blockquote>
“The only programming project with no disagreement whatsoever on code
formatting is the one you work on alone.” — Jeff Atwood.
</blockquote>

* You are not a human code compiler/compressor, so don’t try to be one.
* All code in any code-base should look like a single person typed it, no
  matter how many people contributed.
* Strictly enforce the agreed upon style.
* If in doubt when deciding upon a style, use existing, common patterns.


<a name="whitespace"></a>
## 2. Whitespace

Only one style should exist across the entire source of your code-base. Always
be consistent in your use of whitespace. Use whitespace to improve readability.

* _Never_ mix spaces and tabs for indentation.
* Choose between soft indents —spaces— or real tabs. Stick to your choice
  without fail. _Preference: spaces_.
* If using spaces, choose the number of characters used per indentation level.
  _Preference: 2 spaces_.

Tip: configure your editor to “show invisibles”. This will allow you to
eliminate trailing whitespace, eliminate unintended blank line whitespace,
and avoid polluting diffs.


<a name="format"></a>
## 3. Format

* Always use lowercase tag and attribute names —except in `<!DOCTYPE html>`—.
* Write one discrete element per line.
* Use one additional level of indentation for each nested element.
* Use valueless boolean attributes —e.g. `checked` rather than
  `checked="checked"`—. The same applies to attributes with empty values
  —e.g. `alt` rather than `alt=""`—.
* Always use double quotes to quote attribute values.
* Omit the `type` attributes from `link` stylesheet, `style` and `script`
  elements.
* Always include closing tags.
* Always include a space followed by a trailing slash in self-closing elements
  —e.g. `<img />` rather than `<img>`—.

Example:

```html
<div class="tweet">
  <a href="[url]">
    <img src="[url]" alt />
  </a>
  <p>[text]</p>
  <button disabled>[text]</button>
</div>
```

### Exceptions and Slight Deviations

Elements with multiple attributes can have attributes arranged across multiple
lines in an effort to improve readability and produce more useful diffs.

Example:

```html
<a class="[value]"
 data-action="[value]"
 data-id="[value]"
 href="[url]">
  <span>[text]</span>
</a>
```


<a name="attribute-order"></a>
## 4. Attribute Order

HTML attributes should be listed in an order that reflects the fact that class
names are the primary interface through which CSS and JavaScript select
elements.

1. `class`.
2. `id`.
3. `data-*`.
4. Everything else.

Example:

````html
<a class="[value]" id="[value]" data-name="[value]" href="[url]">[text]</a>
````


<a name="naming"></a>
## 5. Naming

Naming is hard, but very important. It’s a crucial part of the process of
developing a maintainable code base, and ensuring that you have a relatively
scalable interface between your HTML and CSS/JavaScript.

* Use clear, thoughtful, and appropriate names for HTML classes. The names
  should be informative both within HTML and CSS files.
* Avoid _systematic_ use of abbreviated class names. Don’t make things
  difficult to understand.

Example with bad names:

```html
<div class="cb s-scr"></div>
```

```css
.s-scr {
  overflow: auto;
}

.cb {
  background: #bada55;
}
```

Example with better names:

```html
<div class="column-body is-scrollable"></div>
```

```css
.is-scrollable {
  overflow: auto;
}

.column-body {
  background: #bada55;
}
```


<a name="example"></a>
## 6. Practical Example

An example of various conventions.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>[text]</title>
    <link rel="stylesheet" href="[url]" />
    <script src="[url]"></script>
  </head>
  <body>
    <article class="post" id="1234">

      <time class="timestamp">March 15, 2012</time>
      <a data-id="1234"
       data-analytics-category="[value]"
       data-analytics-action="[value]"
       href="[url]">[text]</a>

      <ul>
        <li>
          <a href="[url]">[text]</a>
          <img src="[url]" alt="[text]" />
        </li>
        <li>
          <a href="[url]">[text]</a>
          <img src="[url]" alt />
        </li>
      </ul>

      <a class="link-complex" href="[url]">
        <span>[text]</span>
        [text]
      </a>

      <input value="text" readonly />

    </article>
  </body>
</html>
```


<a name="afterword"></a>
## 7. Afterword

It doesn’t actually matter which code style is used in a code-base. What
really does matter is that everyone on the team sticks with those conventions
and uses them consistently.

So, if you’re editing code, take a closer look and determine its style. If
spaces are being used for indentation, use spaces; if single quotes are being
used for any given purpose, use single quotes too. Bottom line, do what is
being done. Period.

The whole point of having a style guide is to have a common vocabulary, so
people can concentrate on what you’re saying rather than on how you’re saying
it. If code you add to a file looks drastically different from the existing
code around it, it throws readers out of their rhythm when they go to read it.
Avoid this. __Be consistent__.


<a name="acknowledgements"></a>
## Acknowledgements

Based on [Idiomatic HTML](//github.com/necolas/idiomatic-html).
Inspired on [Idiomatic CSS](//github.com/necolas/idiomatic-css),
[Idiomatic JavaScript](//github.com/rwldrn/idiomatic.js),
[Google HTML/CSS Style Guide](//google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml),
[Google JavaScript Style Guide](//google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml) &
many others.


<a name="license"></a>
## License

_Principles of Writing Consistent, Idiomatic HTML_ is licensed under
[Creative Commons](//creativecommons.org/licenses/by/3.0/).
This applies to all documents in this repository.