# Engineering Interview Questions
A collection of sample interview questions to ask engineers. 

## Data Wrangling

### String Encoding
Build a function that takes as input a string of letters and returns an encoded version of the string. The encoding scheme converts letters regardless of case, that appear once in the string to the '#' character and letters that appear more than once to the '&' character. Each letter should be encoded according to this scheme. The following strings and their conversions are provided as examples.
Input -> Output
one ->  ###
three -> ###&&
Heartbreak hotel -> &&&&&#&&&##&#&&#

```python
def duplicate_encode(word):
   '''
   :returns: new_string -> str. Encoded version of the input     string.
   '''
   new_string = ''
   # TODO Implement encoder
   return new_string
```
### Solutions and Follow ups
List comprehension solution
```python
def duplicate_encode(word):
    """ One liner via list comprehension solution """
    return "".join(["#" if word.lower().count(c) == 1 else "&" for c in word.lower()])
```
O(2n) solution
```python

import collections
def duplicate_encode(word):
    """ O(2n) solution """
    new_string = ''
    word = word.lower()
    d = collections.defaultdict(int)
    for c in word:
        d[c] += 1
    for c in word:
        new_string = new_string + ('#' if d[c] == 1 else '&')
    return new_string
```

Follow up questions

- What are potential problems with solutions utilizing `count()`
- What are potential downsides implementing a solution similar to the O(2n) solution?
- Are there cases where one would be more appropriate than the other?
