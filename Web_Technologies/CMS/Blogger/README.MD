# Blogger by Google


## [Widget Tags for Layouts](Widget-Tags.MD)
Content Reference: https://support.google.com/blogger/answer/46995

## [Layouts Data Tags](Layouts-Data-Tags.MD)
Content Reference: https://support.google.com/blogger/answer/47270

## [Page Elements Tags for Layouts](Page-Elements-Tags.MD)
Content Reference: https://support.google.com/blogger/answer/46888

## [Customize CSS Tags for Layouts](Customize-CSS-Tags.MD)
Content Reference: https://support.google.com/blogger/answer/46871


## Methodologies

### Creating Variables

```css
.blog-name h1,.blog-name h1 a{
color:$(blog.title.color);
font:$(blog.title.font);
line-height:$(blog.title.font.size);
text-transform:uppercase
}
```

```html
<Variable name="blog.title.font" description="Blog Title Font" type="font" default="$(alata24)"  value="700 24px Alata, sans-serif"/>

<Variable name="alata24" description="Medium-size bold font (eg: subscribe popup title)" type="font" default="700 24px Alata, sans-serif" hideEditor="true"  value="700 24px Alata, sans-serif"/>
```

### Querying

https://blog.technical0812.com/search?updated-max=2020-12-25T00:30:00%2B05:30&max-results=7

https://blog.technical0812.com/search?q=apple

https://blog.technical0812.com/search/label/IoT

### Global Standard Variables

Variable | Description
---------|------------
data:view.title.escaped | To Create Page Title


### Page Links Format
- Blog Page (example.com/[YYYY/MM]/post-name.html)
- Page (example.com/p/page-name.html)


### Include & Includables Example

- <b:section
- <b:widget
- <b:includable

**Includable Example**

```html
// Create Section
<b:section id='testing'>    

// Create Widget | if type is 'Something' then id should be 'Something1', 'Something2', 'Something(n)'
<b:widget id="PageList2" type='PageList' locked="yes">

// Create Includable
<b:includable id='test1'>
<!-- Write Something Here -->
</b:includable>
      
</b:widget>
  
</b:section>
```

**Include Example**

```html
\\ Use it either in the same widget OR in another widget of the same section OR use it in different section
<b:include name='test1'/>
```



## Troubleshooting

### Error interpreting blog theme

Errors | Solution
-------|---------
Unknown runtime binding: includable in widget | All includables should be under widget in section
Error during evaluation of \<include-name\> | All include should be either used in the same widget OR in another widget of the same section OR use it in different section
