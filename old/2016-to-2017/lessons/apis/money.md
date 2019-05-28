# Money Conversion
In this section we are going to use an API to fetch the conversion rate between Pounds and US Dollars and convert Pounds to Dollars.

To get started make a new HTML file, today we are mainly going to be focusing on JavaScript and we are going to use a library called jQuery.

Firstly, copy this template:
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Currency Converter</title>
  </head>
  <body>

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
  </body>
</html>
```

If you open a browser now you will just have a blank page with the title "Currency Converter".

Now we need to add some boxes to type numbers into. To make a number box you can type this:
```
<input type="number" class="form-control" id="pounds" placeholder="Pounds">
```

Now make another one for Dollars and make sure you change the `id` and `placeholder`.

If there's already numbers in the boxes how will we know which is which? Let's add labels.

Put a `p` tag around the `input` so the `input` is inside the `p` tag. And just before the `input` add a sensible label like "Pounds". Do this for the Dollars box too.

If you've done it correctly you should get something like:

![](https://i.imgur.com/aWh75vh.png)

And you should only be able to type numbers into the boxes.

Now we are going to add some JavaScript to the equation to make it work.

Make a new `script` tag after the other `script` tag that imports jQuery.

To do a request in jQuery you need to do this:

```
$.get("< A URL >", function(data, status){

});
```

Where it says "< A URL >", as you can guess we need to put our URL which is `"http://api.fixer.io/latest?base=GBP`. You can go to that in a browser and see what it is outputting.

Now after the URL there is a function, this function is called **after** the request has been made. This is so the code can continue going on without 'blocking up'.

Inside the function we could make it so it puts the exchange rate for dollars and pounds into the box for now. We can do this by:

```
$("#dollars").val(data.rates.USD);
```

The `$` tells jQuery that it is needed.

The `("")` selects the element in the web page.

The `#dollars` is the **selector** of our dollars box. `#` is to select an id and a `.` is to select a class. Classes are usually used if more than one thing is being used, normally in CSS. IDs are ususally used when there is only one of the things. Like here, there is only one Pound box and only one Dollar box.

The `.val()` sets the **value** of the box. This only works for inputs. If you wanted to set the text of a `p` element you would use `.text()` or `.html()`. `.val()`, `.text()` and `.html()` can all be used without anything in the brackets to get the html, value or text of an element.

Now add another line to set the pounds box to `1`.

Your web page should now look like this:

![](https://i.imgur.com/MsyNBud.png)

Now we are going to make it so if you change the Pounds it changes the Dollars.

We need to make a **listener** to trigger when a key has gone up to update the Dollars box:
*Make this inside the `$.get`.*
```
$("#pounds").keyup(function() {

});
```

The above will call the function whenever a key has gone up *so in our case when the user has finished typing*. Inside here we want to set the value of `#dollars` to the exchange rate times the value of `#pounds`.

Now if you type 100 into the Pounds box the Dollars box changes. You should get something like this:

![](https://i.imgur.com/LWjZgzu.png)

## Challenges
* Make it so when you type in the Dollars box it changes the Pounds.
* Make it so both boxes are rounded to the nearest penny/cent.
* Use **CSS** to make the page Christmas colours.
