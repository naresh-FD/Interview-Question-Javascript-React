# Javascript Interview questions

#### 1. Write a function that takes in a string as input and returns the reversed version of the string.

```javascript
function reverseString(str) {
  let reversed = '';
  for (let i = str.length - 1; i >= 0; i--) {
    reversed += str[i];
  }
  return reversed;
}
```

### 2.Write a function that takes in a string as input and returns the first non-repeating character in the string. If all characters are repeating, return null.

```javascript
function firstNonRepeatingCharacter(str) {
  const charCount = {};
  for (const char of str) {
    charCount[char] = charCount[char] + 1 || 1;
  }
  for (const char of str) {
    if (charCount[char] === 1) {
      return char;
    }
  }
  return null;
}
```

### 3.Implement a stack class that supports push, pop, and peek operations.

```javascript
class Stack {
  constructor() {
    this.items = [];
  }
  push(element) {
    this.items.push(element);
  }
  pop() {
    if (this.items.length === 0) {
      return null;
    }
    return this.items.pop();
  }
  peek() {
    if (this.items.length === 0) {
      return null;
    }
    return this.items[this.items.length - 1];
  }
}
```

### 4. Implement a queue class that supports enqueue, dequeue, and peek operations.

```javascript
class Queue {
  constructor() {
    this.items = [];
  }
  enqueue(element) {
    this.items.push(element);
  }
  dequeue() {
    if (this.items.length === 0) {
      return null;
    }
    return this.items.shift();
  }
  peek() {
    if (this.items.length === 0) {
      return null;
    }
    return this.items[0];
  }
}
```

### 4.Write a function that takes in a string as input and returns the length of the longest substring that doesn't have any repeating characters.

```javascript
function longestSubstringWithoutRepeatingCharacters(str) {
  const charSet = new Set();
  let longest = 0;
  let left = 0;
  let right = 0;
  while (right < str.length) {
    if (!charSet.has(str[right])) {
      charSet.add(str[right]);
      right++;
      longest = Math.max(longest, charSet.size);
    } else {
      charSet.delete(str[left]);
      left++;
    }
  }
  return longest;
}
```

### 6. Write a function that checks if a given number is prime.

```javascript
function isPrime(num) {
  if (num <= 1) return false;
  if (num === 2) return true;
  for (let i = 2; i < num; i++) {
    if (num % i === 0) {
      return false;
    }
  }
  return true;
}
```

### 7. Write a function that finds the nth largest number in an array:

```javascript
function findNthLargest(arr, n) {
  if (n > arr.length) {
    return null;
  }
  const sortedArr = [...arr].sort((a, b) => b - a);
  return sortedArr[n - 1];
}
```

### 7.1 Write a function that finds the nth largest number in an array. If the input array contains duplicate numbers:

```javascript
function findNthLargestDistinct(arr, n) {
  const distinctArr = [...new Set(arr)];
  console.log('text', distinctArr);
  if (n > distinctArr.length) {
    return null;
  }
  const sortedArr = distinctArr.sort((a, b) => b - a);
  return sortedArr[n - 1];
}
```

# 8. Write a function that removes duplicates from an array:

```javascript
function removeDuplicates(arr) {
  let unique = [];
  for (let i = 0; i < arr.length; i++) {
    if (!unique.includes(arr[i])) {
      unique.push(arr[i]);
    }
  }
  return unique;
}
```

# 9. Write a function non repeated function in JavaScript string:

```javascript
function findFirstNonRepeatedChar(str) {
  for (var i = 0; i < str.length; i++) {
    var char = str.charAt(i);
    if (str.indexOf(char) === i && str.indexOf(char, i + 1) === -1) {
      return char;
    }
  }
  return null;
}
```
