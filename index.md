# Regex Cheat Sheet

## Using the Test Method
```javascript
  let myString = "Hello, World!";
  let myRegex = /Hello/;
  let result = myRegex.test(myString);
  console.log(result) // true
```

## Match Literal Strings
```javascript
  let waldoIsHiding = "Somewhere Waldo is hiding in this text.";
  let waldoRegex = /Waldo/;
  let result = waldoRegex.test(waldoIsHiding);
  console.log(result) // true
```

## Match a Literal String with Different Possibilities
```javascript
  let petString = "James has a pet cat.";
  let petRegex = /dog|cat|bird|fish/;
  let result = petRegex.test(petString);
  console.log(result) // true
```

## Ignore Case While Matching
```javascript
  let myString = "German";
  let fccRegex = /gErmaN/i;
  let result = fccRegex.test(myString);
  console.log(result) // true
```

## Extract Matches
```javascript
  let extractStr = "Extract the word 'coding' from this string.";
  let codingRegex = /coding/;
  let result = extractStr.match(codingRegex);
  console.log(result) // '[ 'coding', index: 18, input: 'Extract the word \'coding\' from this string.' ]
```

## Find More Than the First Match
```javascript
  let twinkleStar = "Twinkle, twinkle, little star";
  let starRegex = /Twinkle/ig;
  let result = twinkleStar.match(starRegex);
  console.log(result) // [ 'Twinkle', 'twinkle' ]
```

## Match Anything with Wildcard Period
```javascript
  let exampleStr = "Let's have fun with regular expressions!";
  let unRegex = /.un/;
  let result = unRegex.test(exampleStr);
  console.log(result) // true
```

## Match Single Character with Multiple Possibilities
```javascript
  let quoteSample = "Beware of bugs in the above code; I have only proved it correct, not tried it.";
  let vowelRegex = /[aeiou]/ig;
  let result = quoteSample.match(vowelRegex);
  console.log(result) // [ 'e', 'a', 'e', 'o', u', i', 'e', 'a', 'o', 'e', 'o', 'e', 'I', 'a', 'e', 'o', 'o', 'e', 'i', 'o', 'e', 'o', 'i', 'e', 'i' ]
```

## Match Letters of the Alphabet
```javascript
  let quoteSample = "The quick brown fox jumps over the lazy dog.";
  let alphabetRegex = /[a-z]/ig;
  let result = quoteSample.match(alphabetRegex);
  console.log(result) // [ 'T', 'h', 'e', 'q', 'u', 'i', 'c', 'k', 'b', 'r', 'o', 'w', 'n', 'f', 'o', 'x', 'j', 'u', 'm', 'p', 's', 'o', 'v', 'e', 'r', 't', 'h', 'e', 'l', 'a', 'z', 'y', 'd', 'o', 'g' ]
```

## Match Numbers and Letters of the Alphabet
```javascript
  let quoteSample = "Blueberry 3.141592653s are delicious.";
  let myRegex = /[h-s2-6]/ig;
  let result = quoteSample.match(myRegex); 
  console.log(result) // [ 'l', 'r', 'r', '3', '4', '5', '2', '6', '5', '3', 's', 'r', 'l', 'i', 'i', 'o', 's' ]
```

## Match Single Characters Not Specified
```javascript
  let quoteSample = "3 blind mice.";
  let myRegex = /[^0-9aeiou]/ig;
  let result = quoteSample.match(myRegex);
  console.log(result) // [ ' ', 'b', 'l', 'n', 'd', ' ', 'm', 'c', '.' ]
```

## Match Characters that Occur One or More Times
```javascript
  let difficultSpelling = "Mississippi";
  let myRegex = /s+/ig;
  let result = difficultSpelling.match(myRegex);
  console.log(result) // [ 'ss', 'ss' ]
```