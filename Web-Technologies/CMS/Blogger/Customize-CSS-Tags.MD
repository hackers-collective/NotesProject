## Customize CSS Tags for Layouts


### Set up the variables

In the ```<head>``` section of your code, you'll need to have a pair of ```<b:skin> </b:skin>``` tags.

The CSS style declarations will go in between those tags, along with the variable names that make your design work with the Fonts and Colors page.

**Example**

```html
<head>

...
<b:skin>
  <style type='text/css'>
  /*
   * Variable definitions:
   * <Variable name='bgcolor' description='Page Background Color' type='color' default='#fff'/>
   */
  body {
    background: $bgcolor;
    margin: 0;
    padding: 40px 20px;
  }
  </style>
</b:skin>
</head>
```

_The CSS code enclosed in /* and */ comment tags won't be shown on your blog.

There will be a list of variables here, one for each font or color that you want to be editable from the "Fonts and Colors" tab. Each variable is required to have the information shown in the example above and described here:

- name - May contain letters or numbers. Each name in your template must be unique.
- description - Add a description to appear in "Fonts and Colors" section.
- type - "Font" or "color."
- default - The default value. For colors, this should be a hexadecimal color code, for example #FF0066. For fonts, it will be a list of the form font-style font-weight font-size font-family.


### Use the variables 

After the variables are set up, when you want to use the value of a variable, enter ```$variable_name``` in the ```b:skin``` css.

**Variable types**

> The template designer has editing support for a specific set of CSS variable types. To set the type of variable:
> - color variables will provide a color palette for selection in the template designer.
> - font variables will provide a font selection, with size and bold or italics options, in the template designer.

In the example above, there is a variable called ```bgcolor```, which is set to white (#fff). In the next code, it says: ```background: $bgcolor```. This turns the background white, and you can change it in the "Fonts and Colors" section.

**Note:** _You don't need to create variables for other types of CSS attributes. These can be included in the CSS just as they normally would be (as with the_ ```margin:``` _and_ ```padding:``` _attributes in the example above).
