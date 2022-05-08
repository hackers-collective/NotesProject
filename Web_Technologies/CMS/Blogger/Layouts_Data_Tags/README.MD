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

### Blog Posts

This is the central part of any blog. Here's all the data available in this widget.

- **feedLinks:** A list of feeds for this page. On the main page, this will contain the main blog feeds; on item pages, this will also contain comments feeds. Each item in this list contains the following:
  - **url:** The feed URL
  - **name:** The feed name (i.e, 'Posts' or 'Comments').
  - **feedType:** The type of feed (Atom or RSS).
  - **mimeType:** The mime type of the feed.
- **olderPageUrl:** If there are older posts than the ones on the current page, this is a URL to those posts. Context-sensitive for page type. (Not all pages will have this link.)
- **olderPageTitle:** Title of the link to the older page of posts.
- **newerPageUrl:** The newwer equivalent of olderPageUrl.
- **newerPageTitle:** The newer equivalent of olderPageTitle.
- **commentLabel:** The phrase to use to show the number of comments, e.g. "comments."
- **authorLabel:** The phrase to use to indicate who wrote the post, e.g. "posted by."
- **timestampLabel:** The phrase to use to indicate when the post was written, e.g. "posted at."
- **postLabelsLabel:** Phrase to introduce the list of post labels, e.g. "labels for this post."
- **backlinksLabel:** Phrase to describe backlinks to this post, e.g. "links to this post."
- **posts:** A list of all posts for this page. Each post contains the following:
  - **dateHeader:** The date of this post, only present if this is the first post in the list that was posted on this day.
  - **id:** The numeric post ID.
  - **title:** The post's title.
  - **body:** The content of the post.
  - **author:** The display name of the post author.
  - **url:** The permalink of this post.
  - **timestamp:** The post's timestamp. Unlike dateHeader, this exists for every post.
  - **labels:** The lsit of the post's labels. Each label contains the following:
    - **name:** The label text.
    - **url:** The URL of the page thatlists all post in this blog with this label.
    - **isLast:** True or false. Whether this label is the last one in the list (useful for placing commas).
  - **allowComments:** 'True' if this post allows comments.
  - **numComments:** This number of comments on this post.
  - **showBacklinks:** Whether to show backlinks for this post.
  - **numBacklinks:** Number of backlinks for this post.
  - **addCommentUrl:** The URL of the 'add a comment' form for this post.
  - **emailPostUrl:** The URL of the 'email this post' form for this post.
  - **editUrl:** The URL of the 'email this post' form for this post.
  - **feedLinks:** A list of feeds specific to this post. (This is different from the overall blog feedLinks, as it may contain a feed for the post's comments, for instance.) Each contains the following:
    - **url:** The feed URL.
    - **name:** The feed name (e.g. 'Posts' or 'Comments').
    - **feedType:** The type of feed (Atom or RSS).
    - **mimeType:** The mime type of the feed.
  - **comments:** A list of all comments for this post (on item pages only). Each contains the following:
    - **id:** The numeric ID of the comment.
    - **body:** The body of the comment.
    - **timestamp:** The time the comment was created.
    - **author:** The display name of the comment's author, or 'Anonymous'.
    - **authorUrl:** URL of the comment author's profile, if the comment is not anonymous.
    - **deleteUrl:** The URL for deleting this comment.
    - **isDeleted:** Whether this comment has been deleted. (The text of deleted comments is replaced with a placeholder.)

### Blog Archives

The different styles provided here are for the different default options on the Page Elements tab. If you're designing a new version, it's easiest to use 'FLAT' as the style, and then manipulate the rest of the data as desired.

- **title:** The title of the widget.
- **style:** One of 'MENU', 'FLAT', or 'HIERARCHY'.
- **data:** A list of each archive unit, each of which contains:
  - **name:** The name of this archive unit, each of which contains:
  - **url:** The link to the page containing posts from this interval.
  - **post-count:** How many posts there are in this interval.

### Profile Widget

For a blog with a singe author, the profile widget contains the following information. Note that to access different parts of the ```photo``` data, you'll use notation such as ```<data:photo.url/>```.

- **title:** The title of the widget.
- **userUrl:** The author's profile URL.
- **location:** The location from the author's profile.
- **aboutme:** The "About Me" information from the profile.
- **displayname:** The author's display name.
- **photo:** The user's profile photo, mode up of the following:
  - **url:** The photo URL.
  - **width:** The photo's width, in pixels.
  - **height:** The photo's height, in pixels.
  - **alt:** The "alt" text for the photo.

On team blogs, the profile widget contains less information about more authors, as follows.

- **title:** The title of the widget.
- **authors:** The list of all authors, each of which contains the following:
  - **displayName:** The author's display name.
  - **userURL:** The author's profile URL.

_If you want to design your template to handle both single- and multiple-author blogs, you can use the)_ ```data:team``` _variable to distinguish between the two cases. E.g._

```html
<b:if cond='data:team=="true"'>
  (display multiple authors)
</b:if>
```

### Text / HTML / JavaScript Widget

The Text Widget and the HTMl/JavaScript widget work the same way and have the same two pieces of data.

- **title:** The widget's title.
- **content:** The content of the widget.

### Feed Widget

A feed widget's content is dynamically loaded using Google AJAX API after blog is rendered in a browser. It can be styled only using CSS.

- **title:** The widget's title
- **feedUrl:** The URL of the feed.

### Picture Widget

A picture widget contains a single image, and provides all the relevant data for that image.

- **title:** The title of the widget.
- **sourceUrl:** The URL of the image.
- **width:** The image's width, in pixels.
- **height:** The image's height, in pixels.
- **caption:** The image caption.

### Labels Widget

The labels widget includes a list of all labels that are in use on the blog.

- **title:** The widget title.
- **labels:** The list of labels, each of which contains:
  - **name:** The text of the label.
  - **count:** How many posts have this label.
  - **url:** A link to a page displaying posts with this label.

### List Widget

The simplest form of a list. Each item is just a single piece of text, without any different types of data within it.

- **title:** The widget title.
- **items:** The list of items.

### Link List Widget

A slighly fancier list, where each item has two parts to it: the text and the link.

- **title:** The widget title.
- **links:** The lsit of links, each of which contains:
  - **name:** The link's text.
  - **target:** The link's URL.

### Logo Widget

It doesn't get any simpler than this one. Just one piece of data here.

- **fullButton:** The URL of the Blogger button you've selected.
