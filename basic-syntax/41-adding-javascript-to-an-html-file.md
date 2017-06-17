# Adding JavaScript to an HTML File

JavaScript is related to an HTML file using the `<script>` tag. There are a few different ways to load JavaScript in an HTML file. The two primary choices are between inline JavaScript and external JavaScript. For the most part, we will use external JavaScript files because that allows for a nicer organization of our project and a better "separation of concerns". When we want to edit JS we shouldn't have to deal with all the HTML code in our page. The JS files are probably plenty long enough.

In each case, inline or external, we use a `<script>` tag. Read more about the `<script>` tag [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script).

## Inline JavaScript

Inline JavaScript is written into the HTML of a document and contained in a `<script>` tag. There are cases where this is necessary in a production website/app, and it can be a nice way to experiment with specific features or solutions. 

Here is an example of inline JavaScript:

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Hello World</title>
</head>
<body>
  <h1 id="page-title">Replace This Text</h1>
  <script>
    let heading = document.querySelector("#page-title");
    heading.innerHTML = "Hello World!";
  </script>
</body>
</html>
```

## External JavaScript

