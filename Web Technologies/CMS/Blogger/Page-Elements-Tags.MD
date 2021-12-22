## Page Elements Tags for Layouts

The ```<body>``` section of a layout theme is made up of sections and widgets.

- Sections are areas of your page, such as a sidebar, footer.
- A widget is a page element such as a page, a blogroll, or anything else you can add from the "Page Elements" tab.

You can include any HTML you like around the sections in your theme.


### Sections

Each section in your theme has opening and closing tags that look something like this.

```html
<b:section id='header' class='header' maxwidgets="1" showaddelement="no">
</b:section>
```

**<b:section> tag attributes**

- **id** - (Required) A unique name, with letters and numbers only.
- **class** - (Optional) Common class names are "navbar", "header", "main", "sidebar", and "footer." If you change themes later, these names help Blogger determine how to transfer your content.
- **maxwidgets** - (Optional) The maximum number of widgets to allow in this section. If you don't specify a limit, there won't be one.
- **showaddelement** - (Optional) Can be "yes" or "no," with "yes" as the default. This determines whether the Page Elements tab will show the 'Add a Page Element' link in this section.
- **growth** - (Optional) Can be 'horizontal' or 'vertical,' with 'vertical' as the default. This determines whether widgets within this section are arranged side-by-side or stacked.

_A section can only contain widgets. To insert extra code within a section, split the section into two or more new sections._



### Widgets

A widget is represented by a single tag, which is a placeholder to indicate how the widget should be handled in the Page Elements tab.

Some examples of widgets (one for a page header and one for a list) are:

```html
<b:widget id="header" type='HeaderView' locked="yes"/>
<b:widget id="myList" type='ListView' locked="no" title="My Favorite Things"/>
<b:widget id="BlogArchive1" locked="false" mobile="yes" title="Blog Archive" type="BlogArchive"/>
```


**Widget attributes**

- **id** - (Required) May contain letters and numbers only, and each widget ID in your theme should be unique. A widget's ID cannot be changed without deleting the widget and creating a new one.
- **type** - (Required) Indicates the kind of widget.
- **locked** - (Optional) Can be "yes" or "no" as the default. A locked widget cannot be moved or deleted from the Page Elements tab.
- **title** - (Optional) If no display title is specified, a default title such as "List1" will be used.
- **pageType** - (Optional) Can be "all," "archive," "main," or "item," with "al" as the default. The widget will display only on the designated pages of your blog. (All widgets display on the Page Elements tab, regardless of their pageType.)
- **mobile** - (Optional) Can be "yes," "no," or "only" with "default" as the default. This decides if the widget will be displayed on mobile or not. Only Header, Blog, Profile, PageList, AdSense, Attribution will be displayed on mobile when the mobile attribute is "default."

**Note:** _In your published blog, all_ ```<b:section>``` _and_ ```<b:widget>``` _tags will be replaced with_ ```<div>``` _tags, which will have the specified ID. This will allow you to refer to, for example, div#header or div#myList in your CSS._
