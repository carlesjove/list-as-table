List as table
==============
A Sass mixin for displaying definition lists as tables for mobile-first happiness.

See a demo [here](http://carlus.cat/static/list-as-table/).

How To Use
-----------

Create a list of semantically correct definition lists:

```html
<ul>
  <li>
    <dl>
      <dt>#</dt>
        <dd>17644</dd>
      <dt>Title</dt>
        <dd>Hello World</dd>
      <dt>Author</dt>
        <dd>James Joyce</dd>
      <dt>Total reads</dt>
        <dd>5</dd>
    </dl>
  </li>
  ...
</ul>

```

In your stylesheet, include `list_as_table` and use the mixin 

```sass
@import "path/to/list_as_table";

ul {
  // Mobile styles here (if you want some)
  li {
    dt, dd {
      margin: 0;
      padding: 0;
      float: left;
    }

    dt {
      font-weight: bold;
    }

    dd + dt {
      clear: left;
    }
  }

  // Style list as table
  @media only screen and (min-width: 960px) {
    @include list-as-table(4); // You must specify the column number, which is de <dt> count
  }
}

// See the example files for a full list of available options
```

Options
--------
`$columns`: int. The number of columns (in other words, the number of `<dt>`tags)  

`$cell_padding`: (optional) Cell padding, in `em` units 

`$head_bg`: (optional) Background color for the table header 

`$head_color`: (optional) Text color for the table header

`$striped`: (optional) `bool`. Whether you want the table striped or not. Default is `true`

`$strip_colors`: (optional) `list`. A two item list with the rows colors. Order is odd, even. Example: `(#fff, #f5f5f5) // White for odd and light gray for even`

`$strip_rule`: (optional) Whether to strip odd or even rows. Values must be `odd` or `even` 

`$borders`: (optional) `bool`. Whether the table should have borders or not. Default is `false` 

`$border_color`: (optional) Border color

`$nested_cells`: (optional) `list`. If a column has more than one children (that is, a `<dt>` tag has multiple `<dd>`) specify the cases in a list. Example: `(2,3) // One column has two nested cells, and another has 3`

Changelog
---------
== 0.1.4 ==
- Prevent unwanted goddam margins ruin the thing

== 0.1.3 ==
- Fixed undefined variable usage
- dt margin issue

== 0.1.2 ==
- Prevent possible style conflicts

License
--------
The one that says that you can do whatever you like with this.
