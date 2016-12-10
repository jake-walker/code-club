# Introduction
APIs are provided by many sites to allow developers to use their services in their application.
## Example
Imagine there is a currency API. This API might allow a developer to get the exchange rate from Pounds to the currency. To get the exchange rate for Dollars the developer might need to make a program to go to `theapi.co.uk/currency/USD`. This site might then return:

```
{
  currency: "USD",
  exchangeRate: 1.26
}
```

Now the developer can write some code to fetch the information from this site and convert Pounds to Dollars.
# Real World APIs
Now you know a bit about APIs, here are some ones from popular companies that you've probably heard of:
* **Google** - Lots of the services you might use on Google have an API. Google Calendar for example might allow developers to see what is in your calendar.
* **Amazon** - Amazon have an API which allows you to search for products and find information out about them.
* **Met Office** - Allows developers to collect the latest weather information.
* and the list goes on...

So as you can see quite a few big companies have APIs. In this lesson we are going to use an API using a programming language called Node.js which is build on JavaScript so it is very similar.
