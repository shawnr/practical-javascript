# Extra Practice

Remember: Learning to program takes practice! It helps to see concepts over and over, and it's always good to try things more than once. We learn much more the second time we do something. Use the exercises and additional self-checks below to practice.

## 1. Looping and Conditionals

```js
let maxNum = 20;

for (let i=1; i<=maxNum; i++) {
    if (i % 2 === 0) {
        console.log(`${i} is even.`;
    } else {
        console.log(`${i} is odd.`);
    }
}
```
<quiz name="">
    <question>
        <p>What is the name of the counter variable in this <code>for</code> loop?</p>
        <answer><code>maxNum</code></answer>
        <answer correct><code>i</code></answer>
        <answer><code>console</code></answer>
        <answer><code>undefined</code></answer>
        <explanation>The name of the counter variable is <code>i</code>.</explanation>
    </question>
    <question>
        <p>How many times will this loop execute?</p>
        <answer>1</answer>
        <answer>19</answer>
        <answer correct>20</answer>
        <answer>21</answer>
        <explanation>This loop will execute 20 times.</explanation>
    </question>
    <question>
        <p>What is the starting value of <code>i</code>?</p>
        <answer>0</answer>
        <answer correct>1</answer>
        <answer>20</answer>
        <answer>undefined</answer>
        <explanation>The starting value of <code>i</code> is 1.</explanation>
    </question>
    <question>
        <p>What is the conditional statement checking for?</p>
        <answer correct>That the remainder of <code>i</code> divided by <code>2</code> is <code>0</code>.</answer>
        <answer>That the remainder of <code>maxNum</code> divided by <code>2</code> is <code>0</code>.</answer>
        <answer>That <code>i</code> divided by <code>2</code> is <code>0</code>.</answer>
        <answer>That <code>i</code> divided by <code>2</code> is even.</answer>
        <explanation>The conditional is checking that the remainder of <code>i</code> divided by <code>2</code> is <code>0</code>.</explanation>
    </question>
    <question>
        <p>What happens to <code>i</code> on each loop?</p>
        <answer>It is decreased by one.</answer>
        <answer correct>It is increased by one.</answer>
        <answer>It is multiplied by 2.</answer>
        <answer>It is multiplied by 10%.</answer>
        <explanation>The variable <code>i</code> is increased by one on each iteration of the loop.</explanation>
    </question>
    <question>
        <p>What would the loop output when <code>i</code> equals <code>7</code>?</p>
        <answer><code>"7 is even."</code></answer>
        <answer correct><code>"7 is odd."</code></answer>
        <explanation>When <code>i</code> is equal to <code>7</code>, the console log would be <code>"7 is odd."</code>.</explanation>
    </question>
    <question>
        <p>What would the loop output when the condition <code>(i % 2 === 0)</code> equals <code>false</code>?</p>
        <answer><code>`${i} is even.`</code></answer>
        <answer correct><code>`${i} is odd.`</code></answer>
        <explanation>When <code>(i % 2 === 0)</code> equals <code>false</code>, the console log would be <code>`${i} is odd.`</code>.</explanation>
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
