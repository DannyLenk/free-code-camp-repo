# Standard README.md File

![Design preview for the Space tourism website coding challenge](./assets/preview.jpg)

## Welcome! 👋
## Table of contents

- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- CSS utility classes

## Basic JS

### Return Early Pattern for functions

```js
// Setup
function abTest(a, b) {
  // Only change code below this line
  if (a < 0 || b < 0) {
     return
  }
  // Only change code above this line
  return Math.round(Math.pow(Math.sqrt(a) + Math.sqrt(b), 2));
}
abTest(2,2);
```

### Replace loops using recursion
```js
function sum(arr, n) {
   // Only change code below this line
   if (n <= 0) {
      return 0;
   } else {
      return sum(arr, n - 1) + arr[n - 1];
   }
   // Only change code above this line
}

console.log(sum([2, 3, 4, 5], 3));
```
### Countdown resursion
```js
// Only change code below this line
function countdown(n){
   if (n <= 0) {
      return [];
   } else {
      let numArr = countdown(n - 1);
      numArr.unshift(n);
      return numArr;
   }
}
console.log(countdown(10));
// Only change code above this line
```
### Use recursion to create range of numbers
```js
function rangeOfNumbers(startNum, endNum) {
   if (endNum < startNum) {
      return [];
   } else {
      const numArr = rangeOfNumbers(startNum, endNum - 1);
      numArr.push(endNum);
      return numArr;
   }
};
```

## ES 6

### Prevent object mutation
```js
  function freezeObj() {
     const MATH_CONSTANTS = {
        PI: 3.14
     };
     // Only change code below this line
     Object.freeze(MATH_CONSTANTS);

     // Only change code above this line
     try {
        MATH_CONSTANTS.PI = 99;
     } catch(ex) {
        console.log(ex);
     }
     return MATH_CONSTANTS.PI;
  }
  const PI = freezeObj();
```

### Set Default Parameters for Your Functions
```js
  const increment = (number, value = 1) => number + value;
```

### Use the Rest Parameter with Function Parameters
```js
  const sum = (...args) => args.reduce((a, b) => a + b, 0);
  console.log(sum(3, 4, 1))
```

### Use the Spread Operator to Evaluate Arrays In-Place
```js
// var arr = [6, 89, 3, 45];
// var maximus = Math.max.apply(null, arr);
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr);

```

### Use Destructuring Assignment to Extract Values from Objects
```js
const HIGH_TEMPERATURES = {
  yesterday: 75,
  today: 77,
  tomorrow: 80
};
// Only change code below this line
// const today = HIGH_TEMPERATURES.today;
// const tomorrow = HIGH_TEMPERATURES.tomorrow;
const { today, tomorrow } = HIGH_TEMPERATURES;
// Only change code above this line
```

### Use Destructuring Assignment to Assign Variables from Objects
```js
   const HIGH_TEMPERATURES = {
      yesterday: 75,
      today: 77,
      tomorrow: 80
   };
   // Only change code below this line
   // const highToday = HIGH_TEMPERATURES.today;
   // const highTomorrow = HIGH_TEMPERATURES.tomorrow;
   const {today: highToday, tomorrow: highTomorrow} = HIGH_TEMPERATURES;
   // Only change code above this line
```

### Use Destructuring Assignment to Assign Variables from Nested Objects
```js
const LOCAL_FORECAST = {
  yesterday: { low: 61, high: 75 },
  today: { low: 64, high: 77 },
  tomorrow: { low: 68, high: 80 }
};
// Only change code below this line
// const lowToday = LOCAL_FORECAST.today.low;
// const highToday = LOCAL_FORECAST.today.high;
const { today: { low: lowToday, high: highToday }} = LOCAL_FORECAST;
// Only change code above this line
```

### Use Destructuring Assignment to Assign Variables from Arrays
```js
let a = 8, b = 6;
// Only change code below this line
[a, b] = [b, a];
```

### Use Destructuring Assignment with the Rest Parameter to Reassign Array Elements
```js
   const source = [1,2,3,4,5,6,7,8,9,10];
      function removeFirstTwo(list) {
         // Only change code below this line
         const [a, b, ...arr] = list;
         // Only change code above this line
         return arr;
      }
   const arr = removeFirstTwo(source);
```

### Use Destructuring Assignment to Pass an Object as a Function's Parameters
```js
const stats = {
  max: 56.78,
  standard_deviation: 4.34,
  median: 34.54,
  mode: 23.87,
  min: -0.75,
  average: 35.85
};

// Only change code below this line
const half = ({max, min}) => (max + min) / 2.0; 
// Only change code above this line
```

### Write Concise Declarative Functions with ES6
```js
// Only change code below this line
const bicycle = {
  gear: 2,
  setGear(newGear) {
    this.gear = newGear;
  }
};
// Only change code above this line
bicycle.setGear(3);
console.log(bicycle.gear);
```

### Use class Syntax to Define a Constructor Function
```js
// Only change code below this line
class Vegetable {
  constructor(name) {
    this.name = name;
  }
}
// Only change code above this line

const carrot = new Vegetable('carrot');
console.log(carrot.name); // Should display 'carrot'
```

### use getter and setter
```js
   class Thermostat {
      constructor(fTemp) {
         this._fTemp = fTemp;
      }

      get temperature() {
         return 5/9 * (this._fTemp - 32);
      }
      set temperature(newTemp) {
         this._fTemp = newTemp * 9.0 / 5 + 32;
      }
   }

   const thermos = new Thermostat(76);
   let temp = thermos.temperature;
   thermos.temperature = 26;
   temp = thermos.temperature;
```

### Use export to Share a Code Block
```js
   const uppercaseString = (string) => {
      return string.toUpperCase();
   }
   const lowercaseString = (string) => {
      return string.toLowerCase()
   }
   export { uppercaseString, lowercaseString }
```

### Reuse JavaScript Code Using import
```js
import { uppercaseString, lowercaseString } from './string_functions.js';  
// Only change code above this line

uppercaseString("hello");
lowercaseString("WORLD!");
```

### Use * to Import Everything from a File
```js
import * as stringFunctions from './string_functions.js';
// Only change code above this line

stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```

### Create an Export Fallback with export default
```js
export default function(x, y) {
  return x - y;
}
```

### Import a Default Export
```js
import subtract from './math_functions.js';
subtract(7,4);
```

### Complete a Promise with resolve and reject
```js
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer represents a response from a server
  let responseFromServer;
    
  if(responseFromServer) {
    resolve('We got the data');
  } else {  
    reject('Data not received');
  }
});
```

### Handle a Fulfilled Promise with then
```js
   const makeServerRequest = new Promise((resolve, reject) => {
      // responseFromServer is set to true to represent a successful response from a server
      let responseFromServer = true;
         
      if(responseFromServer) {
         resolve("We got the data");
      } else {  
         reject("Data not received");
      }
   });
   makeServerRequest.then(result => {
      console.log(result);
   });
```

### Handle a Rejected Promise with catch
```js
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer is set to false to represent an unsuccessful response from a server
  let responseFromServer = false;
    
  if(responseFromServer) {
    resolve("We got the data");
  } else {  
    reject("Data not received");
  }
});

makeServerRequest.then(result => {
  console.log(result);
});
makeServerRequest.catch(error => {
  console.log(error);
})
```

## Regular Expressions

### Using the Test Method
```js
let petString = "James has a pet cat.";
let petRegex = /dog|cat|bird|fish/; // Change this line
let result = petRegex.test(petString);
```

### Ignore Case While Matching
```js
let myString = "freeCodeCamp";
let fccRegex = /freecodecamp/i; // Change this line
let result = fccRegex.test(myString);
```

### Extract Matches
```js
let extractStr = "Extract the word 'coding' from this string.";
let codingRegex = /coding/; // Change this line
let result = extractStr.match(codingRegex); // Change this line
```

### Find More Than the First Match
```js
let twinkleStar = "Twinkle, twinkle, little star";
let starRegex = /twinkle/ig; // Change this line
let result = twinkleStar.match(starRegex); // Change this line
```

### Match Anything with Wildcard Period
```js
let exampleStr = "Let's have fun with regular expressions!";
let unRegex = /.un/; // Change this line
let result = unRegex.test(exampleStr);
```

### Match Single Character with Multiple Possibilities
```js
let quoteSample = "Beware of bugs in the above code; I have only proved it correct, not tried it.";
let vowelRegex = /[aeiou]/gi; // Change this line
let result = quoteSample.match(vowelRegex); // Change this line
```

### Match Letters of the Alphabet
```js
let quoteSample = "The quick brown fox jumps over the lazy dog.";
let alphabetRegex = /[a-z]/gi; // Change this line
let result = quoteSample.match(alphabetRegex); // Change this line
```

### Match Numbers and Letters of the Alphabet
```js
let quoteSample = "Blueberry 3.141592653s are delicious.";
let myRegex = /[h-s2-6]/ig; // Change this line
let result = quoteSample.match(myRegex); // Change this line
console.log(result)
```

### Match Single Characters Not Specified
```js
let quoteSample = "3 blind mice.";
let myRegex = /[^aeiou0-9]/ig; // Change this line
let result = quoteSample.match(myRegex); // Change this line
console.log(result);
```

### Match Characters that Occur One or More Times
```js
let difficultSpelling = "Mississippi";
let myRegex = /s+/ig; // Change this line
let result = difficultSpelling.match(myRegex);
console.log(result)
```

### Match Characters that Occur Zero or More Times
```js
// Only change code below this line
let chewieRegex = /Aa*/; // Change this line
// Only change code above this line
let result = chewieQuote.match(chewieRegex);
```

### Find Characters with Lazy Matching
```js
let text = "<h1>Winter is coming</h1>";
let myRegex = /<.*?>/; // Change this line
let result = text.match(myRegex);
```

### Find One or More Criminals in a Hunt
```js
let reCriminals = /C+/; // Change this line
```

### Match Beginning String Patterns
```js
let rickyAndCal = "Cal and Ricky both like racing.";
let calRegex = /^Cal/; // Change this line
let result = calRegex.test(rickyAndCal);
```

### Match Ending String Patterns
```js
let caboose = "The last car on a train is the caboose";
let lastRegex = /caboose$/; // Change this line
let result = lastRegex.test(caboose);
```

### Match All Letters and Numbers
```js
let quoteSample = "The five boxing wizards jump quickly.";
let alphabetRegexV2 = /\w/g; // Change this line
let result = quoteSample.match(alphabetRegexV2).length;
console.log(result);
```

### Match Everything But Letters and Numbers
```js
let quoteSample = "The five boxing wizards jump quickly.";
let nonAlphabetRegex = /\W/g; // Change this line
let result = quoteSample.match(nonAlphabetRegex).length;
console.log(result);
```

### Match All Numbers
```js
let movieName = "2001: A Space Odyssey";
let numRegex = /\d/g; // Change this line
let result = movieName.match(numRegex).length;
console.log(result);
```

### Match All Non-Numbers
```js
let movieName = "2001: A Space Odyssey";
let noNumRegex = /\D/g; // Change this line
let result = movieName.match(noNumRegex).length;
console.log(result)
```

### Restrict Possible Usernames
```js
let username = "JackOfAllTrades";
let userCheck = /^[a-z][a-z]+\d*$|^[a-z]\d\d+$/i; // Change this line
let result = userCheck.test(username);
```

### Match Whitespace
```js
let sample = "Whitespace is important in separating words";
let countWhiteSpace = /\s/g; // Change this line
let result = sample.match(countWhiteSpace);
console.log(result)
```

### Match Non-Whitespace Characters
```js
let sample = "Whitespace is important in separating words";
let countNonWhiteSpace = /\S/g; // Change this line
let result = sample.match(countNonWhiteSpace);
```

### Specify Upper and Lower Number of Matches
```js
let ohStr = "Ohhh no";
let ohRegex = /Oh{3,6}\sno/; // Change this line
let result = ohRegex.test(ohStr);
```











### Continued development

* CSS grid;

*Use this section to outline areas that you want to continue focusing on in future projects. These could be concepts you're still not completely comfortable with or techniques you found useful that you want to refine and perfect.

### Useful resources

- [Array.prototype.reduce()](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce) - Helped me understand the reduce() method;

- [Git + GitHub](https://www.youtube.com/watch?v=RGOj5yH7evk) - the basic git commands (Youtube).
- [The Markdown Guide](https://www.markdownguide.org/) - for more help with writing markdown (Article).

## Author

- Github - [DannyLenk](https://github.com/DannyLenk)
- Frontend Mentor - [@DannyLenk](https://www.frontendmentor.io/profile/DannyLenk)
- Facebook - [Valerii Danylenko](https://www.facebook.com/valerii.danylenko)
- LinkedIn - [Valerii Danylenko](https://www.linkedin.com/in/valerii-danylenko-74379212b)
- insta - [valeriidanylenko](https://www.instagram.com/valeriidanylenko/?hl=ru)

## Acknowledgments

Thank you, Kevin Powell. Hats off to you and your clear English.
