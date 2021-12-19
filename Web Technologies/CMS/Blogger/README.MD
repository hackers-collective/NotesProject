# Blogger by Google


## Widget Tags for Layouts

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
