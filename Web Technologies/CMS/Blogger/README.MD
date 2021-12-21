# Blogger by Google


## Widget Tags for Layouts
Content Reference: https://support.google.com/blogger/answer/46995

### _Types of tags_

### Includes (b:include)

**When to use includes**
  
  Includes are most useful if you have a section of code that you want to re-use in several different places.
  
  To do this, you need to write the content inside a b:includable, then use b:include wherever you want it to appear.


**Format**

```html
<b:includable id='main' var='thiswidget'>
  [Insert Whatever content You Want Here]
</b:includable>
```


**Attributes**

- **id** (required): A unique identifier. Each widget must have on includable with ```id='main'```.
- **var** (optional): An identifier for referencing data within this section.

_If you make more includables with different IDs, they won't displayed automatically. However, if you make an includable with ```id='new'```, then you can reference it in your main includable with ```<b:include name='new' /> ``` and it will display that way._

The attributes for the b:include tag are as follows:
- **name** (required): An identifier that must match the ID of an existing ```b:includable``` in the same widget.
- **data** (optional): An expression or piece of data to pass on to the includable section. This will become the value of the var attribute in the includable.
- **cond** (optional): An expression which causes the include to only execute when its result is true. This is the same as the cond attribute on a b:if


**Example**

Here's an example that shows how to use ```b:includable``` and ```b:include```.
The main thing to understand here is how the "main" section includes the "post" section within it. It passes along a post that it calls "p" and the included section references it as its var "post", then prints the title.
Note that the include only runs while the index is less than 10, so only a max of 10 posts would get rendered in this example (the index starts at 0).

```html
<b:includable id='main'>
  <b:loop var='p' index='index' values='posts'>
    <b:include name='post' data='p' cond='index < 10'/>
  </b:loop>
</b:includable>
<b:includable id='post' var='post'>
  Title: <data.post.title/>
</b:includable>
```

### Date Output (data:)
**Examples**
- **<data.title/>** would print out the title of widget
- **<data.photo.url/>** Size: <data.photo.width /> x <data.photo.height /> would print attributes of a photo component. A photo may have components such as url, height, and width. 

_Using the "." notation indicates that we want the URL for this photo, rather than a URL from something else.

It's like

DATA 

photo ['url: example.com', 'width: 500']

data:photo.url

### Loops (b:loop)
**When to use b:loop**
The ```b:loop``` tag lets you repeat a section of content multiple times. This is most commonly used for printing out each post in a list of posts for a given page, or each comment, or each label, etc.

**Format**
The general format for using loops is this:

```html
<b:loop var='identifier' values='set-of-data'>
  [Repeated Content Goes Here]
</b:loop>
```

_The 'identifier' (i) part can be any name you choose, and will be used to stand in for each new item in the list, each time through the loop. The set of data you specify for the values can be any piece of data as being a list of items._

```html
<b:loop var='i' values='data:posts'>
  <h2><data:i.title/></h2>
</b:loop>
```

Notice how "i" takes on the value of each post in turn, so you can get the title from each one.

**Number Range**
A loop tag allows you to interate accross an inclusive number range, such as '1 to 3', '-3 to -9', where the value of the variable takes the number's value. The following example would create an unordered list of 1, 2 and 3.

```html
<b:loop var='i' values='1 to 3'>
  <li><data:i /></li>
</b:loop>
```
