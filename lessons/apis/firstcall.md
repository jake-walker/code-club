# Your first API call
*'Call' just means to get the information from an API.*

First we need to install a library called `request` which allows us to fetch websites really easily.
```
var request = require("request");
```
Now we need to tell the program how many Pounds we want to convert into Dollars:
```
var pounds = 5;
```
We could add some code to tell the user that the code is running:
```
console.log("My Currency Exchange Program");
```
Then we want to go to `http://api.fixer.io/latest?base=GBP` and get the latest exchange rate with the base currency of GBP. You can go to that link in your browser and see the output. We now need to write some code to fetch the information from that site:
```
request('http://api.fixer.io/latest?base=GBP', function (error, response, body) {
  // do something here
});
```
The code above looks pretty complicated but it's not really. The `request` library needs firstly, a URL to go to then a function to call after it has fetched the information. This function needs the input of `error`, `response` and `body`.

Inside our request function (where it says 'do something here') we need to firstly check that everything has gone OK:
```
if (!error && response.statusCode == 200) {
  // here goes the next line of code in a moment
}
```
The if checks if there are any errors and the status code is 200 (which means everything is OK).

Now we want to display the Pounds in Dollars, inside the `if` statement put:
```
console.log("£" + pounds + " = " + "$" + (JSON.parse(body).rates.USD * pounds));
```
The `JSON.parse(body).rates.USD * pounds` part parses (converts) the JSON (which is what the data is shown as) into something Node can understand more easily, then we do `.rates.USD` which gets the amount of Dollars in Pounds and times it by pounds.

This is what it should look like when you run the script:
![](https://i.imgur.com/6pQHBlU.png)
At the bottom you can see it says:
```
£5 = $6.29
```

> **Challenge: ** Change your code to work with another currency.
