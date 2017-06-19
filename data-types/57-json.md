# JSON
Representing data in structured formats is crucial to many forms of programming, including JavaScript. In order to solve the problem of how to structure data in a way that could be portable online but still retain proper relationships, developers have gravitated towards [JavaScript Object Notation](http://www.json.org/) (commonly called "JSON"). JSON was derived based on how Objects in JavaScript are defined, but it has become a standard data interchange format that is used in virtually every programming language.

Understanding JSON data structures is crucial for developers in any language. But if we're familiar with JavaScript Objects and Arrays, then the JSON data structure does not seem so odd. Here is an example taken from [Wikipedia](https://en.wikipedia.org/wiki/JSON#Comparison_with_other_formats):

```js
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25,
  "address": {
    "streetAddress": "21 2nd Street",
    "city": "New York",
    "state": "NY",
    "postalCode": "10021"
  },
  "phoneNumber": [
    {
      "type": "home",
      "number": "212 555-1234"
    },
    {
      "type": "fax",
      "number": "646 555-4567"
    }
  ],
  "gender": {
    "type": "male"
  }
}
```

JSON data structures are written as "anonymous" Objects. That means there is no `var objectName = ` at the beginning of the data structure. When applications are using JSON, they typically understand that they should interpret the entire structure as a single value. For example, the JSON data above may have come from an API call to a server to fetch the profile information for the user `John Smith`. 

We can see that JSON uses basically the same format as Object definitions in JavaScript. The curly braces (`{ }`) indicate Objects, and the square brackets (`[ ]`) indicate Arrays. Look, for example, at the `phoneNumber` Array: It contains two Objects. Each of the `phoneNumber` objects have two attributes: `type` and `number`. The user `John Smith` has two phone numbers; one of them is his home number and the other is his fax number. This is a common case where users have multiple phone numbers and wish to label each one accordingly. By using the structure of JSON we can easily understand how all this information is related, and we could use all of the information within an application.

