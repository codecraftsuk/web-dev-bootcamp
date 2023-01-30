# 1. HTML

## 1.1. What is HTML?
HTML, which stands for HyperText Markup Language, is a language used to create and structure web pages. It uses elements and tags to define the structure and content of a page.

## 1.2. Anatomy of an HTML Element
An HTML element is made up of an opening tag, content, and a closing tag. The opening tag consists of the element name surrounded by angle brackets, and the closing tag is the same as the opening tag, but with a forward slash before the element name. The content is placed between the opening and closing tags. For example:

``` html
<p>This is a paragraph.</p>
```
## 1.3. HTML Document - Basic Structure
A basic HTML document structure consists of the following elements:

``` html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <!-- Page content goes here -->
  </body>
</html>
```

The `<!DOCTYPE html>` declaration defines the document type. The <html> element acts as a container for the entire page, while the `<head>` element contains information about the page such as the title, and the `<body>` element contains the content of the page.

## 1.4. Build a Basic HTML Document Structure
To build a basic HTML document structure, follow these steps:

1. Open a text editor and create a new file
2. Type the following code:

``` html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <!-- Page content goes here -->
  </body>
</html>
```

3. Save the file with a .html extension, for example: index.html
4. Open the file in a web browser to view the basic HTML structure.

## 1.5. What are Attributes
HTML elements can have attributes, which provide additional information about the element. Attributes are placed in the opening tag, and are made up of a name and a value, separated by an equal sign. For example:

``` html
<a href="https://www.codecrafts.co.uk">Website Link</a>
```
In this example, the href attribute provides the URL for the link.

## 1.6. How to Markup Text
Text in HTML can be marked up using various elements, such as `<p>` for paragraphs, `<h1>` to `<h6>` for headings, `<em>` for emphasis, and `<strong>` for strong emphasis. For example:

``` html
<h1>Heading 1</h1>
<p>This is a paragraph with <em>emphasized</em> text and <strong>strongly emphasized</strong> text.</p>
```

## 1.7. How to Create Links
Links can be created using the `<a>` element and the href attribute. The value of the href attribute is the URL of the linked page. For example:

``` html
<a href="https://www.example.com">Example Link</a>
```

## 1.8. Adding Comments to your HTML Code
Comments in HTML are used to provide explanations or notes in the code. They are ignored by the browser and not displayed on the web page. To add a comment in HTML, use the following syntax:

``` html 
<!-- This is a comment -->
```

## 1.9. What is a Source Code
The source code of a web page is the underlying HTML, CSS, and JavaScript that make up the page. You can view the source code of a web page by right-clicking on the page and selecting "View page source" or "View source" in your web browser. The source code can be edited and changed to modify the appearance and behavior of the web page.

---

# 2. CSS

## 2.1. What is CSS
CSS, which stands for Cascading Style Sheets, is a stylesheet language used to style and layout web pages. It can be used to change the appearance of HTML elements, such as font, color, and spacing.

## 2.2. Methods of applying CSS
There are three ways to apply CSS to a web page:

1. Inline styles, using the style attribute on individual HTML elements.
2. Internal styles, using a `<style>` element in the `<head>` of the HTML document.
3. External styles, using a separate .css file linked to the HTML document using a `<link>` element in the `<head>`of the HTML document.

## 2.3. How to Style Multiple Properties
Multiple CSS properties can be applied to a single HTML element using a semicolon to separate each property. For example:

``` css
p {
  color: red;
  font-size: 16px;
  text-align: center;
}
```

## 2.4. How to Style Multiple Elements
Multiple HTML elements can be styled using a single CSS rule. For example, to style all `<p>` and `<h1>` elements, you can use the following CSS:

``` css
p, h1 {
  color: blue;
  font-family: Arial, sans-serif;
}
```

## 2.5. How to Modify your CSS
CSS can be modified by changing the values of the properties in the CSS rules. The changes will be reflected in the appearance of the web page.

## 2.6. Basic CSS Selectors
CSS selectors are used to select HTML elements to apply styles to. The most common selectors are:

1. Element selector, for example `p {}` to select all `<p>` elements.
2. Class selector, for example `.example {}` to select elements with the class "example".
3. ID selector, for example `#example {}` to select the element with the ID "example".

## 2.7. The CSS Box Model
The CSS box model defines the space occupied by an HTML element, including the content, padding, border, and margin. The width and height of an element are determined by the content, while the padding, border, and margin add extra space around the content.

## 2.8. CSS Padding and Margin Property
The `padding` and `margin` properties define the space inside and outside of an element, respectively. The values can be set in pixels or as a percentage of the parent element's size. For example:

``` css
p {
  padding: 10px;
  margin: 20px;
}
```

## 2.9. CSS Background Property
The `background` property sets the background color or image for an HTML element. For example:


``` css
body {
  background-color: lightgray;
}
```

``` css
body {
  background-image: url(image.jpg);
}
```

## 2.10. Styling a Web Page Title
The title of a web page can be styled using the `<title>` element in the `<head>` of the HTML document and the font-family and color properties in CSS. For example:

HTML:
``` html
<head>
  <title>My Web Page</title>
</head>
```

CSS:

``` css
title {
  font-family: Arial, sans-serif;
  color: blue;
}
```

## 2.11. The CSS Font Property
The font property sets the font for an HTML element. For example:

```css
p {
  font: 16px Arial, sans-serif;
}
```

## 2.12. CSS Display Property
The display property sets the display behavior of an HTML element. For example:

``` css
p {
  display: inline;
}
```

``` css
p {
  display: block;
}
```

## 2.13. Exploring and Using Google Fonts
Google Fonts is a library of free, open-source fonts that can be used on web pages. To use a font from Google Fonts, add the following `<link>` element in the `<head>` of your HTML document:

``` html
<head>
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans&display=swap" rel="stylesheet">
</head>
```

Then, set the font-family property in CSS to the desired font:

``` css
body {
  font-family: 'Open Sans', sans-serif;
}
```

## 2.14. Adding Comments to CSS Code
CSS comments are used to provide explanations or notes in the code. They are ignored by the browser and not displayed on the web page. To add a comment in CSS, use the following syntax:

``` css
/* This is a comment */
```
