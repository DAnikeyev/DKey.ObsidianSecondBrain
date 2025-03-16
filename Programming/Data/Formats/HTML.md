---
date_added: 2024-10-31
tags:
  - data
  - format
  - web
---
Up: [Format](Format.md)
___
 HyperText Markup Language is the standard language used to create and design [Web Page](Web%20Page.md)s on the [Web](Web/Web.md). It provides the basic building blocks for web content by defining the structure of a webpage through the use of elements (or tags). Here’s an overview of HTML:
```html
1. Structure:  
    HTML uses a series of elements such as headings, paragraphs, links, lists, images, and more to structure content on a page. These elements are defined by tags, for example, <code><h1></code> for main headings or <code><p></code> for paragraphs.
    
2. Document Flow:  
    An HTML document is organized hierarchically. It starts with a document type declaration (<code><!DOCTYPE html></code>) followed by the root <code><html></code> element which is divided into the <code><head></code> (containing metadata, links to stylesheets, etc.) and the <code><body></code> (containing the content that is displayed in the browser).
    
3. Semantic Markup:  
    Modern HTML emphasizes semantic elements, which clearly describe their meaning in both the code and visually to the user. Examples include <code><header></code>, <code><footer></code>, <code><article></code>, and <code><section></code>. This practice improves accessibility and search engine optimization (SEO) for the webpage.
    
4. Attributes:  
    Elements can have attributes, which provide additional information. For instance, the <code>src</code> attribute in an <code><img></code> tag defines the image’s location, while the <code>href</code> attribute in an <code><a></code> tag specifies the destination of a link.
    
5. Interactivity and Integration:  
    While HTML is focused on structure, it works in tandem with CSS (for styling) and [JavaScript](JavaScript.md) (for interactivity) to create dynamic and visually appealing web pages.
    
```
Below is an example of a basic HTML document structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Overview of HTML</title>
</head>
<body>
  <h1>Welcome to HTML</h1>
  <p>HTML stands for HyperText Markup Language. It is used to structure information on the web.</p>
  <p>This example shows the basic skeleton of an HTML document.</p>
</body>
</html>
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
