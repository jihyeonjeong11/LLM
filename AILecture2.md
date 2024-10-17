https://v2.scrimba.com/prompt-engineering-for-web-developers-c02o/~01

## AI Assisted Coding

Actual coding stuffs.

## Generate code with pseudocode

pseudo style1:

```
/* Prompt
Please write a JavaScript function:

function getBookById(bookArr, id)
    for each book in bookArr
        if book.id === id
            return book
        else return error object "No book found"
 */

  function getBookById(bookArr, id) {
    for(let i = 0; i < bookArr.length; i++) {
        if(bookArr[i].id === id) {
            return bookArr[i];
        }
    }
    return { error: "No book found" };
}
```

```
Generate some funny book mock data to test this function.

let books = [
{id: 1, title: 'How to Train Your Hamster', author: 'Timmy Tumbles'},
{id: 2, title: 'The Art of Potato Sculpting', author: 'Potato Picasso'},
{id: 3, title: 'Zen and the Art of Lawnmower Maintenance', author: 'Grassy Noel'},
{id: 4, title: 'To Serve Man: A Cookbook', author: 'Chef Kanamit'},
{id: 5, title: 'Why Unicorns Don’t Do Taxes', author: 'Rainbow Glittersparkle'},
{id: 6, title: 'Bees? An In-Depth Look into Their Questionable Existence', author: 'Buzz Aldrin'},
{id: 7, title: '101 Ways to Use a Spatula', author: 'Flip Flapjack'}
];

```

pseudo style2: more conversational way

```
/* Prompt:
Write a JavaScript function findBookById which takes two arguments, bookArr and id
- for each book in bookArr, compare each bookArr id with passed in id
  - if found, return book
  - if not found, return error object, "Sorry, no book found"
 */

  function findBookById(bookArr, id) {
    // Iterate over each book in the bookArr
    for (let i = 0; i < bookArr.length; i++) {
        // If the id of the current book equals the passed id
        if (bookArr[i].id === id) {
            // return the book
            return bookArr[i];
        }
    }
    // If no book found, return an error object
    return {error: "Sorry, no book found"};
  }
```

practice:

```
/*
Want practice? Write detailed pseudocode for the following functions and prompt
ChatGPT to write them for you:

1. A function that adds two numbers
2. A function that adds all the numbers in an array
3. A function that looks for a user.id in a user array and returns an error if not found
4. A function to count vowels in a string
5. A function that finds the highest number in an array
*/


```

## Generate code using a pseudo language.

```
# ComponentName

State:
- stateVariable: initialValue

Props:
- propName: propType

Render:
- Description of render content

Event Handlers:
- handlerName: Description of handler functionality


//eg)

# ComponentName

State:
- activeLink: 0

Props:
- navLinks: object

Render:
- Accepts an array of objects, each representing a link in the nav menu. Each object contains:
    - url name (Home, About, Contact Us, etc)
    - url
- Render the list of links

Event Handlers:
- handleClick: When a nav menu item is clicked, update activeLink with nav menu item index
```

```
Create a pseudo language that will help me quickly describe
to you how to provide sample code and styles for an HTML form.
Respond with a template I can use, as well as a sample element.



```

### Remember to remind the template to ChatGPT after 7 ~ 10 interactions.

## Generate Edge cases !!important

```
// prompt1

// Write a JavaScript function that takes in an array and returns a new array with any duplicate items removed.

function removeDuplicates(arr) {
  return [...new Set(arr)];
}

// prompt 2

// list edge cases for generated function

Empty Array:

Input: []
Expected Output: []
Explanation: An empty array should return an empty array.
Array with All Unique Elements:

Input: [1, 2, 3]
Expected Output: [1, 2, 3]
Explanation: The function should return the same array if there are no duplicates.
Array with All Identical Elements:

Input: [1, 1, 1, 1]
Expected Output: [1]
Explanation: The function should return a single unique element from an array of identical elements.
Array with Different Data Types:

Input: [1, '1', 2, 2, '2']
Expected Output: [1, '1', 2, '2']
Explanation: The function should differentiate between numbers and strings, treating 1 and '1' as distinct.
Array with null, undefined, and NaN:

Input: [null, undefined, NaN, NaN, undefined]
Expected Output: [null, undefined, NaN]
Explanation: NaN is a special case where NaN !== NaN, but Set treats all NaN values as equal. Also, null and undefined should be treated as distinct values.
Array with Objects and Arrays as Elements:

Input: [{a: 1}, {a: 1}, [1, 2], [1, 2]]
Expected Output: [{a: 1}, {a: 1}, [1, 2], [1, 2]]
Explanation: Objects and arrays are compared by reference, not value. Even if they have the same contents, they are considered different unless they reference the same object.
Large Array:

Input: Large array with many duplicate elements.
Expected Output: A de-duplicated array.
Explanation: The function should handle large arrays efficiently.
Mixed Case Sensitivity in Strings:

Input: ['a', 'A', 'b', 'B']
Expected Output: ['a', 'A', 'b', 'B']
Explanation: The function should treat 'a' and 'A' as distinct unless case insensitivity is explicitly required.
Sparse Arrays (arrays with "holes"):

Input: Array(5) (creates a sparse array of length 5 with empty slots)
Expected Output: The result should maintain the structure or ignore empty slots based on how the function is designed to handle them.
Array with false, 0, '' (falsy values):

Input: [false, 0, '', false, 0, '']
Expected Output: [false, 0, '']
Explanation: Falsy values should not be removed unless they are duplicates.
Handling these edge cases ensures that your removeDuplicates function is robust across different scenarios.

prompt 3:

Prompt: Give me the edge case tests in a single code block,
and denote the edge case as part of the console.log.
Example: console.log('empty array: ', removeDuplicates([]))

```

and propmpt to handle some cases for my need.

## Generate Test Cases and practice.

```
function chunkArray(array, size) {
    let chunks = [];
    for (let i = 0; i < array.length; i += size) {
        chunks.push(array.slice(i, i + size));
    }
    return chunks;
}

console.log(chunkArray([1,2,3,4], 2)); // [[1,2], [3,4]]

// Prompt: Call this function with 3 test inputs and console.log results.
// Test Case 1
let array1 = [1, 2, 3, 4, 5, 6, 7, 8, 9];
let size1 = 3;
console.log(chunkArray(array1, size1));  // Expected output: [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

// Test Case 2
let array2 = ["a", "b", "c", "d", "e"];
let size2 = 2;
console.log(chunkArray(array2, size2));  // Expected output: [['a', 'b'], ['c', 'd'], ['e']]

// Test Case 3
let array3 = [true, false, true, false, true];
let size3 = 1;
console.log(chunkArray(array3, size3));  // Expected output: [[true], [false], [true], [false], [true]]

/* Edge Cases
Input Array is null or undefined:
// chunkArray(null, 2);

Chunk Size is Zero or Negative:
// chunkArray([1, 2, 3, 4, 5], 0); // infinite loop!

Chunk Size is null, undefined, or Not a Number:
// chunkArray([1, 2, 3, 4, 5], null);
// chunkArray([1, 2, 3, 4, 5], "two");
*/

revised function

function chunkArray(array, size) {
    // Check if the first argument is an array
    if (!Array.isArray(array)) {
        throw new Error('The first argument must be an array.');
    }

    // Check if the second argument is a positive integer
    if (typeof size !== 'number' || size <= 0 || Math.floor(size) !== size) {
        throw new Error('The second argument must be a positive integer.');
    }

    let chunks = [];
    for (let i = 0; i < array.length; i += size) {
        chunks.push(array.slice(i, i + size));
    }
    return chunks;
}



```

## Generating Error messages

- Custom Error message

## Converting code

- imagine converting existing CSS to tailwinds format.
- convert CSV to JSON

## Documenting the code !!important

- useJSDOC format to document blocks, Applying Intellisense.
- Utilize further converting it "Document this component using StoryBook."

- Advanced use: Something fundamental:

```
  prompt 1:
  I want to create a simple Javascript style guide. Ask me 10 questions about best practices and style conventions and use my answers to write a style guide.

  Variable Declaration: Do you prefer using var, let, or const for variable declaration? When should each be used?

  Semicolons: Do you prefer mandatory semicolons at the end of each statement, or do you use automatic semicolon insertion (ASI)?

  Quotes: Do you prefer single quotes (') or double quotes (") for strings?

  Indentation: How many spaces do you prefer for indentation (2, 4, or tabs)?

  Arrow Functions vs. Regular Functions: When should you use arrow functions (() => {}) versus regular function declarations (function() {})?

  Line Length: What is the maximum recommended line length in your codebase (e.g., 80, 100, or 120 characters)?

  Object and Array Destructuring: Do you prefer using destructuring to access object or array properties, or do you stick to traditional access (e.g., arr[0], obj.prop)?

  Comments: How do you prefer to write comments? Do you use single-line (//) or block comments (/* */)? What are your guidelines for when to comment?

  Trailing Commas: Do you prefer including trailing commas in object and array literals, or do you avoid them?

  Naming Conventions: What are your preferred naming conventions for variables, functions, and classes (e.g., camelCase for variables and functions, PascalCase for classes)?

  prompt2:
  Use latest Eslint unicorn ruleset.

```

```

```

## Learn with AI

- Summarize and explain info in a variety of ways
- Find Learning resources
- Create a study guide and schedyle
- Test yourself

- Summaries
- Start with broad and drilling into detailes
- instruct your AI to:
  - Assume a specific audience
  - Assume a specific experience or skill level
  - Metaphor or spefcific example

```
1: Please suggest 4 advanced Javascript topics that every junior or intermediate developer should study
2: Let's concentrate on Async programming. Please tell me more about callbacks. Explain the concept as if I am a beginner and include a code example.
3. I still don't understand. Can you explain callbacks using a metaphor, and can you provide a couple more use cases?
4. Explain callback functions to me as if I'm 5 years old.
```

- Find learning resources
- Create study guide and schedule
- Test yourself

- List 5 great articles I can read to understand dynamic programming.
  -> Get materials in one place
- Scheduling, Creating guide.
- Write me a study guide on Typescript, including outside resources for further study. Assyme I already have an strong grasp of javascript.
- And scheduling your study.

### Watch out for hallucinating, incorrect info, outdated sources, non-existent sources.

- Quiz me on Typescript!
- 5 small coding problems about higher order function in Javascript.
- Questions you don't know - ask steps above to learn enough to feel confident giving an answer.

## Explore APIs with Gemini

https://gemini.google.com/app

- Chatgpt's knowledge stops at 2022, which lacks info regarding latest thigs.

- Google Gemini
  Excels at: simplifying information, Conversational exchanges.

### Fact-check needed!

## Git helper

- give me a step by step guide to su submitting a PR for an open source project. I've cloned the repo locally. My branch is called 2343-fix-broken-link, I want to PR into the main branch of a project called super-awesome-proj
- ask chatgpt to deploying nextJS

## When to step back

- Couldn't get desired result after several interaction
- Can't understand the code
- AI keeps saying sorry for inconvinences..
- When Ai keeps forgetting stuffs.
