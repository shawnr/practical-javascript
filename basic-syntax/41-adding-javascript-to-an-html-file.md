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
  <title>External JS Example</title>
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

Notice that the code in the HTML file is the same, except the `<script>` tag has been moved to the `<head>` of the document and we've added two attributes to it. First, we added a `src` attribute that indicates the file we want to load. This link can be either absolute or relative to the HTML file (in this example, it is a relative link). We have also added a `defer` attribute to the `<script>` tag. This tells the browser that it's OK to defer the execution of this script until it has finished rendering the HTML. We typically add either the `async` or `defer` attributes to `<script>` tags when loading external JavaScript files. The `async` attribute tells the browser it's OK to continue rendering the HTML and that it's OK to execute the script whenever the file has finished loading.

In the `main.js` file we have the same code from the previous example. The only difference is that we now have a file that is fully dedicated to JavaScript, affording us a better experience editing the JS functionality on the page.

In general, it's preferable to use external JavaScript when building websites and applications. When building with web technology, each component (HTML, CSS, and JS) tends to become large and complex. It takes a lot of HTML to structure a site and define content. It takes many lines of CSS to define visual styles for a site. And it can take a lot of JavaScript to build all of the functionality wanted for a project. When dealing with large, complex projects, it's helpful to focus on one component at a time. That is easier when each component is contained in dedicated files. (**Note:** For the moment I'm discounting and avoiding discussing technologies like [JSX](https://facebook.github.io/react/docs/jsx-in-depth.html) and how they might be changing this paradigm in the future.)

Similarly to CSS, JavaScript is also something that can be applied to multiple pages within a site. The features we define with JavaScript can be written in a way that they can operate on any page of our site that contains compatible HTML. Being able to link multiple HTML files to the same JavaScript file is a crucial part of making efficient use of the code we write.

For presentation purposes throughout this book, we will occasionally use examples that feature inline JavaScript, but for the most part in the working world we prefer to use external JavaScript files.

<div class="tip-box">

<h3>Blocking Out the Bad Old Days</h3>

<p>Once upon a time, there was a great debate about how to load scripts in HTML. By default, when the browser encounters a <code>script</code> tag with a <code>src</code> attribute it stops rendering the page and waits for that file to download. This is a concept known as "blocking": All processing of the HTML is "blocked" until the linked JavaScript file is downloaded and executed. Unfortunately, this delays the processing of the page and increases the likelihood of user frustration. </p>

<p>To avoid blocking in the past, it was common for developers to put their script tags at the bottom of their HTML file, right before the closing <code>body</code> tag. That was an OK solution, but it put a whole set of important lines at the bottom of the HTML file, which made it a little more difficult to notice as a developer. It was also undesirable because there are situations when we want JavaScript to block the page load (for example, when delivering A/B content tests to end users) and in these cases we would end up with JavaScript in both the <code>head</code> of the document and the <code>body</code> of the document.</p>

<p>The HTML5 specification solved this problem by introducing the <code>async</code> and <code>defer</code> attributes for the <code>script</code> tag. This allows us to keep all of our JavaScript <code>script</code> tags in one place (in the <code>head</code> of our HTML documents) and still avoid blocking the browser's rendering of the page.</p>

</div>

