## Layouts Data Tags

There are many different tags you can use to include specific pieces of data in your template. They will all be formatted as ```<data:name/>``` or ```<data:name1.name2/>```, where ```name``` is the name of the particular piece of data you want to use. In the ```name1.name2``` example, ```name2``` is a particular item within a set of data called ```name1```, e.g. ```photo.url```.

This is a central list of all available data. Since different types of widget use different data, the list is divided into sections based on page elements.


### Globally Available Data

This information applies to the entire page, so you can use it anywhere, unlike other data which can only be used in a specific widget. These should be referenced as part of the overall "blog" data, e.g. as ```<data.blog.title/>```, etc.

- **title:** The blog's title.
- **pageType:** The type of the current page. One of 'item', 'archive', or 'index'.
- **url:** The URL of the current page.
- **homepageUrl:** The homepage of the blog.
- **pageTitle:** The title of the current page. This is often the blog title, but may contain additional information on archive or post pages.
- **encoding:** The encoding to use for the blog, e.g. UTF-8.
- **languageDirection:** Either "ltr" or "rtl" for left-to-right and right-to-left languages, respectively.
- **feedLinks:** The autodiscovery feed links for the page header.


### Page Header

This is a simple widget with just two pieces of data. They can be referenced simply as ```<data:title/>``` and ```<data:description/>```.

- **title:** The blog's title
- **description:** The blog's description.
