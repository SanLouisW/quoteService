<a href="https://996.icu"><img src="https://img.shields.io/badge/link-996.icu-red.svg" alt="996.icu" /></a>

Run:
This is a maven project, to run it, run this command under the project root folder:

mvn package && java -jar target/quoteService-1.0-SNAPSHOT.jar

Creat quote:
use postman
http://localhost:8080/quotes/
POST
{
  "name": "testQuote",
  "quoteLines": [
    {
      "lineNumber": 1,
      "product": {
        "productName": "testProd1",
        "price": 8
      },
      "quantity": 10,
      "discount": 0,
      "totalPrice": 0
    }
  ],
  "discount": 0,
  "totalPrice": 0
}

Check quote:
type in browser:
http://localhost:8080/quotes/testQuote

change discount:
PATCH
{
  "actionType" : "CHANGEDISCOUNT",
  "discount" : 0.10,
  "quoteLine" : {
  }
}

to target a total price:
POST
{
  "name": "testQuote",
  "quoteLines": [
    {
      "lineNumber": 1,
      "product": {
        "productName": "testProd1",
        "price": 5
      },
      "quantity": 10,
      "discount": 0,
      "totalPrice": 0
    }
  ],
  "discount": 0,
  "totalPrice": 0,
  "targetPrice":20
}
