# Regex Cheat Sheet

## Using the Test Method
```js
  let myString = "Hello, World!";
  let myRegex = /Hello/;
  let result = myRegex.test(myString);
  console.log(result) // true
```

## Match Literal Strings
```js
  let waldoIsHiding = "Somewhere Waldo is hiding in this text.";
  let waldoRegex = /Waldo/;
  let result = waldoRegex.test(waldoIsHiding);
  console.log(result) // true
```

## Match a Literal String with Different Possibilities
```js
  let petString = "James has a pet cat.";
  let petRegex = /dog|cat|bird|fish/;
  let result = petRegex.test(petString);
  console.log(result) // true
```

## Ignore Case While Matching
```js
  let myString = "German";
  let fccRegex = /gErmaN/i;
  let result = fccRegex.test(myString);
  console.log(result) // true
```

## Extract Matches
```js
  let extractStr = "Extract the word 'coding' from this string.";
  let codingRegex = /coding/;
  let result = extractStr.match(codingRegex);
  console.log(result) // '[ 'coding', index: 18, input: 'Extract the word \'coding\' from this string.' ]
```

## Find More Than the First Match
```js
  let twinkleStar = "Twinkle, twinkle, little star";
  let starRegex = /Twinkle/ig;
  let result = twinkleStar.match(starRegex);
  console.log(result) // [ 'Twinkle', 'twinkle' ]
```

## Match Anything with Wildcard Period
```js
  let exampleStr = "Let's have fun with regular expressions!";
  let unRegex = /.un/;
  let result = unRegex.test(exampleStr);
  console.log(result) // true
```

## Match Single Character with Multiple Possibilities
```js
  let quoteSample = "Beware of bugs in the above code; I have only proved it correct, not tried it.";
  let vowelRegex = /[aeiou]/ig;
  let result = quoteSample.match(vowelRegex);
  console.log(result) // [ 'e', 'a', 'e', 'o', u', i', 'e', 'a', 'o', 'e', 'o', 'e', 'I', 'a', 'e', 'o', 'o', 'e', 'i', 'o', 'e', 'o', 'i', 'e', 'i' ]
```

## Match Letters of the Alphabet
```js
  let quoteSample = "The quick brown fox jumps over the lazy dog.";
  let alphabetRegex = /[a-z]/ig;
  let result = quoteSample.match(alphabetRegex);
  console.log(result) // [ 'T', 'h', 'e', 'q', 'u', 'i', 'c', 'k', 'b', 'r', 'o', 'w', 'n', 'f', 'o', 'x', 'j', 'u', 'm', 'p', 's', 'o', 'v', 'e', 'r', 't', 'h', 'e', 'l', 'a', 'z', 'y', 'd', 'o', 'g' ]
```

## Match Numbers and Letters of the Alphabet
```js
  let quoteSample = "Blueberry 3.141592653s are delicious.";
  let myRegex = /[h-s2-6]/ig;
  let result = quoteSample.match(myRegex); 
  console.log(result) // [ 'l', 'r', 'r', '3', '4', '5', '2', '6', '5', '3', 's', 'r', 'l', 'i', 'i', 'o', 's' ]
```

## Match Single Characters Not Specified
```js
  let quoteSample = "3 blind mice.";
  let myRegex = /[^0-9aeiou]/ig;
  let result = quoteSample.match(myRegex);
  console.log(result) // [ ' ', 'b', 'l', 'n', 'd', ' ', 'm', 'c', '.' ]
```

## Match Characters that Occur One or More Times
```js
  let difficultSpelling = "Mississippi";
  let myRegex = /s+/ig;
  let result = difficultSpelling.match(myRegex);
  console.log(result) // [ 'ss', 'ss' ]
```

## Match Characters that Occur Zero or More Times
```js
  let chewieQuote = "Aaaaaaaaaaaaaaaarrrgh!"
  let chewieRegex = /Aa*/;
  let result = chewieQuote.match(chewieRegex);
  console.log(result) // [ 'Aaaaaaaaaaaaaaaa', index: 0, input: 'Aaaaaaaaaaaaaaaarrrgh!', groups: undefined ]
```

## Find Characters with Lazy Matching
```js
  let text = "<h1>Winter is coming</h1>";
  let myRegex = /<.*?>/;
  let result = text.match(myRegex);
  console.log(result) // [ '<h1>', index: 0, input: '<h1>Winter is coming</h1>', groups: undefined ]
```

## Match Beginning String Patterns
```js
  let rickyAndCal = "Cal and Ricky both like racing.";
  let calRegex = /^Cal/;
  let result = calRegex.test(rickyAndCal);
  console.log(result) // true
```

## Match Ending String Patterns
```js
  let caboose = "The last car on a train is the caboose";
  let lastRegex = /caboose$/;
  let result = lastRegex.test(caboose);
  console.log(result) // true
```

## Match All Letters and Numbers
***Note:*** shorthand `\w` equals `[A-Za-z0-9_]`
```js
  let quoteSample = "The five boxing wizards jump quickly.";
  let alphabetRegexV2 = /\w/g;
  let result = quoteSample.match(alphabetRegexV2).length;
  console.log(result) // 31
```

## Match Everything But Letters and Numbers
***Note:*** shorthand `\W` equals `[^A-Za-z0-9_]`
```js
  let quoteSample = "The five boxing wizards jump quickly.";
  let nonAlphabetRegex = /\W/g;
  let result = quoteSample.match(nonAlphabetRegex).length;
  console.log(result) // 6
```

## Match All Numbers
***Note:*** shorthand `\d` equals `[0-9]`
```js
  let movieName = "2001: A Space Odyssey";
  let numRegex = /\d/g;
  let result = movieName.match(numRegex).length;
  console.log(result) // 4
```

## Match All Non-Numbers
***Note:*** shorthand `\D` equals `[^0-9]`
```js
  let movieName = "2001: A Space Odyssey";
  let noNumRegex = /\D/g;
  let result = movieName.match(noNumRegex).length;
  console.log(result) // 17
```

## Match Whitespace
```js
  let sample = "Whitespace is important in separating words";
  let countWhiteSpace = /\s/g;
  let result = sample.match(countWhiteSpace);
  console.log(result) // [ ' ', ' ', ' ', ' ', ' ' ]
```

## Match Non-Whitespace Characters
```js
  let sample = "Whitespace is important in separating words";
  let countNonWhiteSpace = /\S/g;
  let result = sample.match(countNonWhiteSpace);
  console.log(result) // [ 'W', 'h', 'i', 't', 'e', 's', 'p', 'a', 'c', 'e', 'i', 's', 'i', 'm', 'p', 'o', 'r', 't', 'a', 'n', 't', 'i', 'n', 's', 'e', 'p', 'a', 'r', 'a', 't', 'i', 'n', 'g', 'w', 'o', 'r', 'd', 's' ]
```

## Specify Upper and Lower Number of Matches
```js
  let ohStr = "Ohhh no";
  let ohRegex = /Oh{3,6}\sno/;
  let result = ohRegex.test(ohStr);
  console.log(result) // true
```

## Specify Only the Lower Number of Matches
```js
  let haStr = "Hazzzzah";
  let haRegex = /Haz{4,}ah/;
  let result = haRegex.test(haStr);
  console.log(result) // true
```

## Specify Exact Number of Matches
```js
  let timStr = "Timmmmber";
  let timRegex = /Tim{4}ber/;
  let result = timRegex.test(timStr);
  console.log(result) // true
```

## Check for All or None
```js
  let favWord = "favorite";
  let favRegex = /favou?rite/;
  let result = favRegex.test(favWord);
  console.log(result) // true
```

## Positive and Negative Lookahead
***Note:*** a positive lookahead is used as `(?=...)` and a negative lookahead is used as `(?!...)`.
```js
  let sampleWord = "astronaut";
  let pwRegex = /(?=\w{6})(?=\w*\d{2})/;
  let result = pwRegex.test(sampleWord);
  console.log(result) // false
```

## Check For Mixed Grouping of Characters
```js
  let myString = "Eleanor Roosevelt";
  let myRegex = /(Franklin|Eleanor).*Roosevelt/;
  let result = myRegex.test(myString);
  console.log(result) // true
```

## Reuse Patterns Using Capture Groups
```js
  let repeatNum = "42 42 42";
  let reRegex = /^(\d+)\s\1\s\1$/;
  let result = reRegex.test(repeatNum);
  console.log(result) // true
```

## Use Capture Groups to Search and Replace
***Note:*** You can access capture groups in the replacement string with dollar signs (`$`).
```js
  let str = "one two three";
  let fixRegex = /(\w+)\s(\w+)\s(\w+)/;
  let replaceText = "$3 $2 $1";
  let result = str.replace(fixRegex, replaceText);
  console.log(result) // "three two one"
```

## Remove Whitespace from Start and End
```js
  let hello = "   Hello, World!  ";
  let wsRegex = /^\s+|\s+$/g;
  let result = hello.replace(wsRegex, "");
  console.log(result) // "Hello, World!"
```