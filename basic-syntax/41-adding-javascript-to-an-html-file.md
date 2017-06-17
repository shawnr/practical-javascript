# Adding JavaScript to an HTML File

JavaScript is related to an HTML file using the `<script>` tag. There are a few different ways to load JavaScript in an HTML file. The two primary choices are between inline JavaScript and external JavaScript. For the most part, we will use external JavaScript files because that allows for a nicer organization of our project and a better "separation of concerns". When we want to edit JS we shouldn't have to deal with all the HTML code in our page. The JS files are probably plenty long enough.

In each case, inline or external, we use a `<script>` tag. Read more about the `<script>` tag [here](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script).

## Inline JavaScript

Inline JavaScript is written into the HTML of a document and contained in a `<script>` tag. There are cases where this is necessary in a production website/app, and it can be a nice way to experiment with specific features or solutions. 

Here is an example of inline JavaScript:

```html
<html>
<head>
  <title>Inline JS Demo</title>
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

The `<script>` tag can be placed in either the `<head>` or `<body>` of the HTML file, and it is executed whenever the browser encounters this tag while rendering the web page. There can be multiple `<script>` tags (and multiple inline scripts) in a single HTML file.

## External JavaScript

External JavaScript is written in a separate file and then linked into the HTML file using a `<script>` tag with the `src` attribute set. We can imagine that we have a website with two files: `index.html` and `main.js`. 

The `index.html` file looks like this:

```html
<html>
<head>
  <title>Hello World</title>
  <script src="main.js" defer></script>
</head>
<body>
  <h1 id="page-title">Replace This Text</h1>
</body>
</html>
```

The `main.js` file looks like this:

```js
  let heading = document.querySelector("#page-title");
  heading.innerHTML = "Hello World!";
```

Notice that the code in the HTML file is the same, except the `<script>` tag has been moved to the `<head>` of the document and we've added two attributes to it. First, we added a `src` attribute that indicates the file we want to load. This link can be either absolute or relative to the HTML file (in this example, it is a relative link). We have also added a `defer` attribute to the `<script>` tag. This tells the browser that it's OK to defer the execution of this script until it has finished rendering the HTML.
