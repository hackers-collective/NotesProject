# Blogger by Google

## [Widget Tags for Layouts](Widget_Tags/README.MD)

Content Reference: <https://support.google.com/blogger/answer/46995>

## [Layouts Data Tags](Layouts_Data_Tags/README.MD)

Content Reference: <https://support.google.com/blogger/answer/47270>

## [Page Elements Tags for Layouts](Page_Elements_Tags/README.MD)

Content Reference: <https://support.google.com/blogger/answer/46888>

## [Customize CSS Tags for Layouts](Customize_CSS_Tags/README.MD)

Content Reference: <https://support.google.com/blogger/answer/46871>

## Layout Structure

Layout of Blogger Made of

- Sections/Widgets

& the CSS is used to style it obviously and bydefault it is automatically converted to DIV as
  e.g:  b:section (in Code) => div (in Render)

```html
<div class='testing section' id='testing'>
```

### Dynamic Layout Format

/home

- Header
- Sidebar
- Footer

- **Blog List**

/blog

- Header
- Sidebar
- Footer

- **Blog Body**

/page

- Header
- Sidebar
- Footer

- **Page Body**

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

<https://blog.technical0812.com/search?updated-max=2020-12-25T00:30:00%2B05:30&max-results=7>

<https://blog.technical0812.com/search?q=apple>

<https://blog.technical0812.com/search/label/IoT>

### Global Standard Variables

Variable | Description | Usage
---------|-------------|------
data:view.title.escaped | To Create Page Title | ```<title>data:view.title.escaped</title>```

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

// Create Widget | | 
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
// Use it either in the same widget OR in another widget of the same section OR use it in different section
<b:include name='test1'/>
```

### Widget Settings

**Example Layout**

```xml
<b:widget-settings>
  <b:widget-setting name='displayHeight'>0</b:widget-setting>
  <b:widget-setting name='useImage'>false</b:widget-setting>
  <b:widget-setting name='imagePlacement'>BEHIND</b:widget-setting>
</b:widget-settings>
```

**Usage**

```xml
<b:includable id='main'>
     <b:if cond='data:useImage'>
       
       <!-- if useImage is False -->

```

### Enable/Disable Adding More Than One Elements (Widgets) in a Section (b:section)

```html
// Add showaddelement attribute which is optional, to enable or disable the adding elements in a single widgets using Layout Editor on Blogger GUI
// Set 'true' OR 'false' accordingly in "showaddelement"
<b:section class='header-pages' id='header-pages' showaddelement='false'>
```

## Recipes

### Creating Next / Prev Buttons for Blog Posts

**Example XML**

```xml
<!-- navigation -->
                  <!-- <b:include name='nextprev' /> --> // Include 


<b:includable id='nextprev'>
  <div class='blog-pager' id='blog-pager'>
    <b:if cond='data:newerPageUrl'>
      <span id='blog-pager-newer-link'>
      <a class='blog-pager-newer-link' expr:href='data:newerPageUrl' expr:id='data:widget.instanceId + &quot;_blog-pager-newer-link&quot;' expr:title='data:newerPageTitle'><data:newerPageTitle/></a>
      </span>
    </b:if>

    <b:if cond='data:olderPageUrl'>
      <span id='blog-pager-older-link'>
      <a class='blog-pager-older-link' expr:href='data:olderPageUrl' expr:id='data:widget.instanceId + &quot;_blog-pager-older-link&quot;' expr:title='data:olderPageTitle'><data:olderPageTitle/></a>
      </span>
    </b:if>

    <a class='home-link' expr:href='data:blog.homepageUrl'><data:homeMsg/></a>

    <b:if cond='data:mobileLinkUrl'>
      <div class='blog-mobile-link'>
        <a expr:href='data:mobileLinkUrl'><data:mobileLinkMsg/></a>
      </div>
    </b:if>

  </div>
  <div class='clear'/>
</b:includable>
```

**Rendered Output Example**

```html
<div class="blog-pager" id="blog-pager">
<span id="blog-pager-older-link">
<a class="blog-pager-older-link" href="https://scriptkkiddie.blogspot.com/2021/02/technical0812com-stay-alert.html" id="Blog1_blog-pager-older-link" title="Older Post">Older Post</a>
</span>
<a class="home-link" href="https://scriptkkiddie.blogspot.com/">Home</a>
</div>
```

## Troubleshooting

### Error interpreting blog theme

Errors | Solution
-------|---------
Unknown runtime binding: includable in widget | All includables should be under widget in section
Error during evaluation of \<include-name\> | All include should be either used inside the same b:section OR in different b:section

### Blogger Template Engine Errors

Errors | Solution
-------|---------
```The new widget id "<b>header11</b>" is invalid for type: <b>PageList</b>``` | if widget type is 'Something' then id should be 'Something1', 'Something2', 'Something(n)'
```The widget with id "<b>header11</b>" cannot contain element: "b:include". A widget can only contain b:includable elements.``` | All b:include should be either used inside the same b:section OR in different b:section
```The widget with id "<b>header</b>" cannot contain element: "div". A widget can only contain b:includable elements.``` | A widget itself is rendered as \<div\> in production, the Validator prevent us to use it again.
```org.xml.sax.SAXParseException; lineNumber: 834; columnNumber: 49; The value of attribute "cond" associated with an element type "b:include" must not contain the '<' character.``` |
