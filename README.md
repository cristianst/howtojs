# howtojs

Basic useful examples to make coding simple.

This sign `->` indicates expected output.

How to...

### Get a randoom boolean

```javascript
const bool = Math.random() > 0.5;

// -> true/false
```

### Duplicate array items

```javascript
const numbers = [1,2,3,4]; // It also works with nested arrays

const doubling = numbers.reduce( (res, current, index, array) => {
    return res.concat([current, current]);
}, []);

// -> [1,1,2,2,3,3,4,4] 

```