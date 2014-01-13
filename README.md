List as table
==============
A Sass mixin for displaying definition lists as table for mobile-first happiness.

See a demo [here](#).

How To Use
-----------

Create a list of semantically correct definition lists:

```
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

```
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
		@include list-as-table(4); // You must tell the column number, which is de <dt> count
	}
}

// See the example files for a full list of available options
```

