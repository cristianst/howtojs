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


### Get the maximum/minimum number in array of objects

```javascript
const items = [
    {
        name: 'Foo',
        price: 200
    },
    {
        name: 'Bar',
        price: 129
    },
    {
        name: 'Qlp',
        price: 1234567
    }
];

// Array of all prices
const prices = items.map((item) => item.price);

const highestPrice = Math.max(...prices);
// -> 1234567

const lowestPrice = Math.min(...prices);
// -> 129
```
