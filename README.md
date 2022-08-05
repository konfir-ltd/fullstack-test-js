# Konfir JavaScript Test

## The challenge

The aim of this exercise is to demonstrate your problem-solving and understanding of JavaScript by implementing something found in every unit testing tool - an "assertEquals" method.

### Instructions

- Fill in the "assertEquals" function provided such that it will correctly compare the "expected" and "actual" parameters.
- You may add more functions.
- We are big on TDD, so we expect you to complete this test using this approach.
- Credit will be given for approach, correctness, clean code, and testing.
- The set of tests provided isn't exhaustive - there are many cases not covered here. We expect you to add additional tests, and to amend ours as you see fit.
- You can take as long as you like to complete the exercise, but for an indicative timescale we expect a senior developer can accomplish this in an hour.

### Additional terms

- Please do not use external libraries (except for a testing library)
- You may of course use any resources you like to assist you with specific techniques, syntax etc - but please do not just copy code.
- Please don't share this exercise with anyone else :)
- We've written some initial tests for you using Jest, which is our testing library of choice. You may use a different library if you wish.

### Example inputs and outputs


| Expected        |       Actual       |                                                                      Result |
|-----------------|:------------------:|----------------------------------------------------------------------------:|
| "abc"           |       "abc"        |                                                                  _No error_ |
| "abcef"         |       "abc"        |                Throws error with message 'Expected "abcef" but found "abc"' |
| ['a']           |      {0: 'a'}      |                 Throws error with message 'Expected array but found object' |
| ['a', 'b']      |  ['a', 'b', 'c']   |             Throws error with message 'Expected array length 2 but found 3' |
| ['a', 'b', 'c'] |  ['a', 'b', 'c']   |                                                                  _No error_ |
| complexObject1  | complexObject1Copy |                                                                  _No error_ |
| complexObject1  |   complexObject2   | Throws error with message 'Expected propB.propA[1].propB "b" but found "c"' |
| complexObject1  |   complexObject3   |          Throws error with message 'Expected propB.propC but was not found' |
| null            |         {}         |        Throws error with message 'Expected type null but found type Object' |


```javascript
  var complexObject1 = {
    propA: 1,
    propB: {
      propA: [1, { propA: 'a', propB: 'b' }, 3],
      propB: 1,
      propC: 2
    }
  };
  var complexObject1Copy = {
    propA: 1,
    propB: {
      propA: [1, { propA: 'a', propB: 'b' }, 3],
      propB: 1,
      propC: 2
    }
  };
  var complexObject2 = {
    propA: 1,
    propB: {
      propB: 1,
      propA: [1, { propA: 'a', propB: 'c' }, 3],
      propC: 2
    }
  };
  var complexObject3 = {
    propA: 1,
    propB: {
      propA: [1, { propA: 'a', propB: 'b' }, 3],
      propB: 1
    }
  };
```

### Instructions for running the tests

With yarn:

- Run `yarn` to install dependencies
- Run `yarn test` to run the tests

With npm:

- Run `npm install`
- Run `npm test`
