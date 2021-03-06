# ForexQuotes

ForexQuotes is a PHP Library for fetching realtime forex quotes

# Table of Contents

- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
    - [List of Symbols available](#get-the-list-of-available-symbols)
    - [Get quotes for specific symbols](#get-quotes-for-specified-symbols)
- [Other implementations](#other-implementations)
    - [API Call: Get all quotes](#get-all-quotes)
    - [API Call: Get specific quotes](#get-specific-quotes)
    - [API Call: Get the symbol list](#get-the-symbol-list)
- [Support / Contact](#support-and-contact)
- [License / Terms](#license-and-terms)

## Requirements
* PHP >= 5.6.4


## Installation
```
composer require oneforge/forexquotes
```
Or in your composer.json
```javascript
"require": {
    "oneforge/forexquotes": "1.0.4"
},
```
## Usage

### Get the list of available symbols:

```php
<?php

use OneForge\ForexQuotes\QuoteRequest;

//Returns an array of symbols, eg: ['EURUSD', 'GBPJPY']
QuoteRequest::getSymbols(); 
```
### Get quotes for specified symbols:
```php
<?php

use OneForge\ForexQuotes\QuoteRequest;

/* 
Returns an array of quotes, eg: 
 [
     [
       "symbol" => "EURUSD",
       "price" => 1.11725,
       "timestamp" => 1496190844,
     ],
     [
       "symbol" => "GBPJPY",
       "price" => 142.037,
       "timestamp" => 1496190844,
     ],
   ]
*/   
QuoteRequest::getQuotes([
    'AUDUSD',
    'GBPJPY'
]);
```

## Other implementations
You can also implement the api directly in any other way you wish. Full documentation is maintained here: <a href="https://1forge.com/forex-data-api">https://1forge.com/forex-data-api</a>


### Get all quotes
#### Request
```
GET https://1forge.com/forex-data-api/1.0.1/quotes
```

#### Response
```javascript
[
   {
      symbol: "AUDJPY",
      timestamp: 1496096332,
      price: 82.726,
   },
   {
      symbol: "AUDUSD",
      timestamp: 1496096332,
      price: 0.74396,
   },
   {
      etc: "........"
   }
]
```

### Get specific quotes
#### Request
```
GET https://1forge.com/forex-data-api/1.0.1/quotes?pairs=EURUSD,GBPJPY,AUDUSD
```

#### Response
```javascript
[
   {
      symbol: "AUDUSD",
      timestamp: 1496096387,
      price: 0.74392,
   },
   {
      symbol: "EURUSD",
      timestamp: 1496096387,
      price: 1.11383,
   },
   {
      symbol: "GBPJPY",
      timestamp: 1496096387,
      price: 142.657,
   }
]
```


### Get the symbol list
#### Request
```
GET https://1forge.com/forex-data-api/1.0.1/symbols
```

#### Response
```javascript
[
   "AUDJPY",
   "AUDUSD",
   "CHFJPY",
   "EURAUD",
   "EURCAD",
   "EURCHF",
   "EURGBP",
   "EURJPY",
   "etc..." 
]
```

## Support and Contact
Please contact me at contact@1forge.com if you have any questions or requests.

## License and Terms 
This library is provided without warranty under the MIT license.
