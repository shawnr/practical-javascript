# Extra Practice

Remember: Learning to program takes practice! It helps to see concepts over and over, and it's always good to try things more than once. We learn much more the second time we do something. Use the exercises and additional self-checks below to practice.

## 1. Data Types and Variable Assignment

```js
let score = 42;

let quote = "Move fast and break stuff.";

let fruits = ['apple', 'orange', 'pear'];

let foo,
    bar,
    baz;

let stopLoop = false;

let userRegistered = true;

```
<quiz name="">
    <question>
        <p>What is the name of the String variable above?</p>
        <answer><code>fruits</code></answer>
        <answer><code>score</code></answer>
        <answer correct><code>quote</code></answer>
        <answer><code>foo</code></answer>
        <explanation>The String variable is <code>quote</code>.</explanation>
    </question>
    <question>
        <p>What Data Type is <code>score</code>?</p>
        <answer>String</answer>
        <answer correct>Number</answer>
        <answer>Boolean</answer>
        <answer>Array</answer>
        <explanation>The <code>score</code> variable is a Number.</explanation>
    </question>
    <question>
        <p>What does <code>fruits.length</code> equal?</p>
        <answer>2</answer>
        <answer>4</answer>
        <answer correct>3</answer>
        <answer>true</answer>
        <explanation><code>fruits.length</code> equals 3.</explanation>
    </question>
    <question>
        <p>What are <code>foo</code>, <code>bar</code>, and <code>baz</code> equal to?</p>
        <answer><code>0</code></answer>
        <answer><code>''</code></answer>
        <answer><code>null</code></answer>
        <answer correct><code>undefined</code></answer>
        <explanation>The variables <code>foo</code>, <code>bar</code>, and <code>baz</code> are equal to <code>undefined</code> because they have been declared but not initialized.</explanation>
    </question>
    <question>
        <p>What is it called when we name a variable without setting a variable (as with <code>foo</code>, <code>bar</code>, and <code>baz</code> in the code above)?</p>
        <answer correct>declaration</answer>
        <answer>initialization</answer>
        <answer>casting</answer>
        <answer>definition</answer>
        <explanation>When we name a variable without assigning a value, we are "declaring" that variable for usage later. Its value will be <code>undefined</code> until it is initialized.</explanation>
    </question>
    <question>
        <p>What Data Types are <code>stopLoop</code> and <code>userRegistered</code>?</p>
        <answer>String</answer>
        <answer>Array</answer>
        <answer>Number</answer>
        <answer correct>Boolean</answer>
        <explanation>The variable <code>baz</code> is equal to <code>undefined</code> because we cannot multiply two Strings.</explanation>
    </question>

</quiz>

## 2. JSON Interpretation

```js
let weatherData = {
    "city": {
        "id": 5809844,
        "name": "Seattle",
        "coord": {
            "lon": -122.3321,
            "lat": 47.6062
        },
        "country": "US",
    },
    "list": [
        {
            "dt": 1500148800,
            "temp": {
                "day": 74.05,
                "min": 55.96,
                "max": 75.09,
                "night": 55.96,
                "eve": 69.6,
                "morn": 68.9
            },
            "pressure": 1024.13,
            "humidity": 51,
            "weather": [
                {
                    "id": 800,
                    "main": "Clear",
                    "description": "sky is clear",
                    "icon": "01d"
                }
            ],
            "speed": 5.17,
            "deg": 222,
            "clouds": 0
        },
        {
            "dt": 1500235200,
            "temp": {
                "day": 67.3,
                "min": 55.78,
                "max": 68.94,
                "night": 56.08,
                "eve": 65.71,
                "morn": 55.78
            },
            "pressure": 1026.81,
            "humidity": 57,
            "weather": [
                {
                    "id": 800,
                    "main": "Clear",
                    "description": "sky is clear",
                    "icon": "01d"
                }
            ],
            "speed": 3.38,
            "deg": 353,
            "clouds": 0
        },
        {
            "dt": 1500321600,
            "temp": {
                "day": 69.85,
                "min": 52.63,
                "max": 70.54,
                "night": 52.63,
                "eve": 66.49,
                "morn": 58.32
            },
            "pressure": 1019.85,
            "humidity": 51,
            "weather": [
                {
                    "id": 801,
                    "main": "Clouds",
                    "description": "few clouds",
                    "icon": "02d"
                }
            ],
            "speed": 6.71,
            "deg": 357,
            "clouds": 12
        }
    ]
}

```

The data above represents a three-day weather forecast for Seattle, WA. Use this data structure to answer the questions below.

<quiz name="">
    <question>
        <p>What is the Data Type of the <code>weatherData.city</code> property above?</p>
        <answer>String</answer>
        <answer>Number</answer>
        <answer>Boolean</answer>
        <answer correct>Object</answer>
        <answer>Array</answer>
        <explanation><code>weatherData.city</code> is an Object.</explanation>
    </question>
    <question>
        <p>What Data Type is <code>weatherData.list</code>?</p>
        <answer>String</answer>
        <answer>Number</answer>
        <answer>Boolean</answer>
        <answer>Object</answer>
        <answer correct>Array</answer>
        <explanation><code>weatherData.list</code> is an Array.</explanation>
    </question>
    <question>
        <p>What does <code>weatherData.list.length</code> equal?</p>
        <answer>2</answer>
        <answer>4</answer>
        <answer correct>3</answer>
        <answer>true</answer>
        <explanation><code>weatherData.length</code> equals 3.</explanation>
    </question>
    <question>
        <p>What does <code>weatherData.list[1].humidity</code> equal?</p>
        <answer><code>58.32</code></answer>
        <answer><code>51</code></answer>
        <answer correct><code>57</code></answer>
        <answer><code>75.3</code></answer>
        <explanation><code>weatherData.list[1].humidity</code> equals <code>57</code>.</explanation>
    </question>
    <question>
        <p>What does <code>weatherData.list[0].temp.eve</code> equal?</p>
        <answer><code>56.7</code></answer>
        <answer correct><code>69.6</code></answer>
        <answer><code>78.3</code></answer>
        <answer><code>82.1</code></answer>
        <explanation><code>weatherData.list[0].temp.eve</code> equals <code>69.6</code>.</explanation>
    </question>
    <question>
        <p>What is the Data Type of <code>weatherData.list[2].weather[0].main</code>?</p>
        <answer correct>String</answer>
        <answer>Number</answer>
        <answer>Boolean</answer>
        <answer>Object</answer>
        <answer>Array</answer>
        <explanation><code>weatherData.list[0].weather[0].main</code> is a String.</explanation>
    </question>
    <question>
        <p>What is the Data Type of <code>weatherData.list[2].weather</code>?</p>
        <answer>String</answer>
        <answer>Number</answer>
        <answer>Boolean</answer>
        <answer>Object</answer>
        <answer correct>Array</answer>
        <explanation><code>weatherData.list[0].weather</code> is an Array.</explanation>
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
