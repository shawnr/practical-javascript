# Extra Practice

Remember: Learning to program takes practice! It helps to see concepts over and over, and it's always good to try things more than once. We learn much more the second time we do something. Use the exercises and additional self-checks below to practice.


## 1. Multiplying Two Numbers
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

## 2. Calculating Area of a Box
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
        <explanation>The name of the function is <code>calculateArea</code>.</explanation>
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

## 3. Scoping Variables
```js

let myText,
    processedText;
    
const stopWords = { // stopWords is an Object defining words that should not be capitalized.
    'of': true,
    'the': true,
    'a': true,
    'an': true,
    'and': true,
    'to': true
}
    

function capitalizeText(text){
    // This function expects a String of text. It breaks apart the String into an 
    // Array of words, then it capitalizes the first letter of each word. Once it has
    // capitalized all words, it returns a new String with capitalized text.
    
    let wordArray = text.split(' '); // Split on space characters.
    let newWordArray = []; // Initialize an Array to store results.
    
    for (word of wordArray){
        if (!stopWords[word]){ // Check to make sure word is not in stopwords list.
            let newFirstLetter = word[0].toUpperCase(); // Change first letter in `word` to uppercase.
            let slicedWord = word.slice(1); // Get the rest of the word after the first letter.
            let newWord = newFirstLetter + slicedWord; // Put the word back together.
            newWordArray.push(newWord); // Add the newWord to the newWordArray of capitalized words.
        } else {
            newWordArray.push(word); // If we hit a stopWord, just put that word back in the list without altering.
        }
    }
    
    var newText = newWordArray.join(' ');
    return newText; // Return the string.
}

myText = "association of code writers";
processedText = capitalizeText(myText);
console.log(processedText);
```
<quiz name="">
    <question>
        <p>The first line of the code above does what?</p>
        <answer>Initializes <code>myText</code> and <code>processedText</code>.</answer>
        <answer>Defines <code>myText</code> and <code>processedText</code>.</answer>
        <answer correct>Declares <code>myText</code> and <code>processedText</code>.</answer>
        <answer>Establishes <code>myText</code> and <code>processedText</code>.</answer>
        <explanation>The first line of the code above <i>declares</i> <code>myText</code> and <code>processedText</code> without initializing them to any value.</explanation>
    </question>
    <question>
        <p>What Data Type is <code>stopWords</code>?</p>
        <answer>String</answer>
        <answer>Number</answer>
        <answer correct>Object</answer>
        <answer>Array</answer>
        <answer>Boolean</answer>
        <explanation>The constant variable <code>stopWords</code> is initialized as an Object.</explanation>
    </question>
    <question>
        <p>When <code>newWordArray</code> is declared, how is it initialized (what value is it made equal to)?</p>
        <answer><code>null</code></answer>
        <answer correct>empty Array</answer>
        <answer><code>0</code></answer>
        <answer>empty Object</answer>
        <explanation>The variable <code>newWordArray</code> is declared and initialized in the same line. It is initialized to an empty Array.</explanation>
    </question>
    <question>
        <p>Why can we use <code>stopWords</code> inside the conditional within the <code>capitalizeText</code> function?</p>
        <answer>Because variables declared with <code>let</code> are global.</answer>
        <answer correct>Because variables declared with <code>let</code> are accessible to the scope in which they are declared and any children scopes.</answer>
        <answer>Because code is magic.</answer>
        <answer>Because special rules of <code>scope</code> apply to conditionals.</answer>
        <explanation>We can access <code>stopWords</code> within the function because variables declared with <code>let</code> are accessible to the scope in which they are declared and any children scopes. The function, and the loop and conditional within, are all structures that create "child scopes" (and these scopes would all contain <code>stopWords</code>).</explanation>
    </question>
    <question multiple>
        <p>What variables defined within the scope of the condition inside <code>capitalizeText()</code> are ONLY accessible WITHIN the "success" or "true" clause of the conditional? (Only the top part of the statement between the first set of braces.)</p>
        <answer><code>word</code></answer>
        <answer correct><code>newFirstLetter</code></answer>
        <answer correct><code>slicedWord</code></answer>
        <answer correct><code>newWord</code></answer>
        <answer><code>newWordArray</code></answer>
        <answer><code>stopWords</code></answer>
        <explanation>The variables <code>newFirstLetter</code>, <code>slicedWord</code>, and <code>newWord</code> are only accessible within the "true" clause of the conditional. <code>word</code> is accessible in the <code>for ... of</code> loop (and, therefore, in all clauses of the conditional). <code>newWordArray</code> is available throughout the entire function, and <code>stopWords</code> is available throughout the entire script.</explanation>
    </question>
    <question>
        <p>Consider this block of code:<br><br>
            <code>
            for (word of wordArray){
                if (!stopWords[word]){
            </code>
            <br><br>
            In this case, what does <code>word</code> equal?
        </p>
        <answer correct>The value of each index in the Array as the loop moves through them.</answer>
        <answer>The value of the entire Array.</answer>
        <answer>The index (number) of each item in the Array.</answer>
        <answer>"42"?</answer>
        <explanation>The <code>word</code> variable contains the value of each index in the Array as the loop moves through them.</explanation>
    </question>
    <question multiple>
        <p>
            Consider this block of code:<br><br>
            <code>
            for (word of wordArray){
                if (!stopWords[word]){
            </code>
            <br><br>
            If we are looping through the <code>wordArray</code> and the value of <code>word</code> is <code>"of"</code>,
            what is the value of <code>stopWords[word]</code>?
        </p>
        <answer correct><code>stopWords.of</code></answer>
        <answer><code>stopWords.word</code></answer>
        <answer correct><code>stopWords["of"]</code></answer>
        <answer><code>stopWords.["of"]</code></answer>
        <explanation>The variable <code>stopWords[word]</code> is evaluates equal to <code>stopWords.of</code> or <code>stopWords["of"]</code>.</explanation>
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
