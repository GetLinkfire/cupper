+++
title = "Components"
tags = ["components", "ember"]
+++

The following are rules and guidelines for developing components in Ember.js at Linkfire.

## Named arguments

Always use named arguments when passing values to a component.


Example: You have a component that displays cool employees. It will display the employee name and their catchphrase like this:

`{{cool-employees name=“Theo” catchphrase="Huh, oh, wait, wat"}}`

Now, in the component you can access the named arguments like this:

`Meet {{@name}}, his catchphrase is {{@catchphrase}}`

instead of

`Meet {{name}}, his catchphrase is {{catchphrase}}`

This provides more clarity of the template and makes it very easy to see what is a named argument and what is not.
