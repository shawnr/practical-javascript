# Extra Practice

Remember: Learning to program takes practice! It helps to see concepts over and over, and it's always good to try things more than once. We learn much more the second time we do something. Use the exercises and additional self-checks below to practice.


# Function Syntax
Review the code, then answer the questions below.

```js
function multiplyNumbers(firstNumber=2, secondNumber=4){
    let product = firstNumber * secondNumber;
    return product;
}

let foo = multiplyNumbers(3,12);

let bar = multiplyNumbers(15,4);

let baz = multiplyNumbers("two","three");

```
<quiz name="">
    <question>
        <p>What is the name of the function?</p>
        <answer><code>function</code></answer>
        <answer correct><code>multiplyNumbers</code></answer>
        <answer><code>foo</code></answer>
        <answer><code>bar</code></answer>
        <explanation>The name of the function is <code>multiplyNumbers</code>.</explanation>
    </question>
    <question>
        <p>What do we call <code>firstNumber</code> and <code>secondNumber</code>?</p>
        <answer>variables</answer>
        <answer correct>parameters</answer>
        <answer>attributes</answer>
        <answer>indices</answer>
        <explanation>In this function declaration, <code>firstNumber</code> and <code>secondNumber</code> are the <i>parameters</i> that this function accepts.</explanation>
    </question>
    <question>
        <p>The <code>firstNumber</code> and <code>secondNumber</code> parameters have values assigned in the function declaration. What do we call this specific type of parameter?</p>
        <answer>assigned parameters</answer>
        <answer>declared parameters</answer>
        <answer correct>default parameters</answer>
        <answer>arguments</answer>
        <explanation>Parameters that have a default value specified in the function declaration are called "default parameters".</explanation>
    </question>
    <question>
        <p>What is <code>foo</code> equal to?</p>
        <answer><code>42</code></answer>
        <answer correct><code>36</code></answer>
        <answer><code>15</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The variable <code>foo</code> is equal to <code>36</code>.</explanation>
    </question>
    <question>
        <p>What is <code>bar</code> equal to?</p>
        <answer><code>55</code></answer>
        <answer><code>19</code></answer>
        <answer correct><code>60</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The variable <code>bar</code> is equal to <code>60</code>.</explanation>
    </question>
    <question>
        <p>What is <code>baz</code> equal to?</p>
        <answer><code>6</code></answer>
        <answer><code>5</code></answer>
        <answer><code>42</code></answer>
        <answer correct><code>undefined</code></answer>
        <explanation>The variable <code>baz</code> is equal to <code>undefined</code> because we cannot multiply two Strings.</explanation>
    </question>

</quiz>

```js
function calculateArea(length, width, units="sq ft"){
    let area = length * width;
    return `${area} ${units}`;
}

let boxLength = 5;
let boxHeight = 12;

let boxArea = calculateArea(boxLength, boxHeight);

```
<quiz name="">
    <question>
        <p>What is the name of the function?</p>
        <answer><code>function</code></answer>
        <answer><code>boxLength</code></answer>
        <answer><code>boxArea</code></answer>
        <answer correct><code>calculateArea</code></answer>
        <explanation>The name of the function is <code>multiplyNumbers</code>.</explanation>
    </question>
    <question multiple>
        <p>What are the names of the parameters this function accepts?</p>
        <answer>boxLength</answer>
        <answer correct>length</answer>
        <answer correct>width</answer>
        <answer correct>units</answer>
        <answer>boxHeight</answer>
        <explanation>In this function declaration, <code>length</code>, <code>width</code>, and <code>units</code> are the parameters we can use with this function.</explanation>
    </question>
    <question>
        <p>What is the expected Data Type for the <code>length</code> and <code>width</code> parameters?</p>
        <answer correct>Number</answer>
        <answer>Array</answer>
        <answer>String</answer>
        <answer>Boolean</answer>
        <explanation>The <code>length</code> and <code>width</code> parameters are expected to be Numbers so they can be multiplied together to calculate the <code>area</code>.</explanation>
    </question>
    <question>
        <p>What is <code>area</code> equal to?</p>
        <answer><code>42</code></answer>
        <answer><code>17</code></answer>
        <answer correct><code>60</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The variable <code>area</code> is equal to <code>60</code>.</explanation>
    </question>
    <question>
        <p>What Data Type is the <code>units</code> parameter?</p>
        <answer>Number</answer>
        <answer>Array</answer>
        <answer correct>String</answer>
        <answer>Boolean</answer>
        <explanation>The parameter <code>units</code> is a String.</explanation>
    </question>
    <question>
        <p>What is <code>boxArea</code> equal to?</p>
        <answer><code>60</code></answer>
        <answer><code>17 sq ft</code></answer>
        <answer correct><code>"60 sq ft"</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The variable <code>boxArea</code> is equal to <code>"60 sq ft"</code>.</explanation>
    </question>
    <question>
        <p>What Data Type is the <code>boxArea</code> variable?</p>
        <answer>Number</answer>
        <answer>Array</answer>
        <answer correct>String</answer>
        <answer>Boolean</answer>
        <explanation>The variable <code>boxArea</code> is a String.</explanation>
    </question>

</quiz>



<div class="no-quiz">
     <h2>Visit Content Online</h2>
     <p> 
         The content on this page has been removed from your PDF 
         or ebook format. You may view the content by visiting
         this book online.
     </p>
</div>
