# howtojs
_Inspired on my daily headaches_ 

Compilation of basic useful JS implementations.
Arrays search, objects, fancy stuff, etc.


This sign `->` indicates expected output.

## How to...

### Get a randoom boolean

```javascript
const bool = Math.random() > 0.5;

// -> true/false
```

### Create an array of N items 

```javascript 
const arr = [...Array(5).keys()]; // N = 5

// -> [0,1,2,3,4]
```

### Duplicate array items

```javascript
const numbers = [1,2,3,4]; // It also works with nested arrays

const doubling = numbers.reduce( (res, current, index, array) => {
    return res.concat([current, current]);
}, []);

// -> [1,1,2,2,3,3,4,4] 
```

Answer in [Stackoverflow](https://stackoverflow.com/a/48792296/2323944)

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

Answer in [Stackoverflow](https://stackoverflow.com/a/48787756/2323944)

### Remove falsy values from array
```javascript
const values = [0, 1, true, false, 'Foo', ''];

const filtered = values.filter(i => i);

// -> [1, true, "Foo"]
```

### Symentric difference of multiple arrays

```javascript
const sym = (...arrays) => {
    // Concat items
    const allItems = arrays.reduce((a,c)=>a.concat(c), []);

    // Identify repeated items
    const repeatedItems = 
        allItems.filter((v,i,a) => a.indexOf(v) !== i);

    const diff = 
        allItems.filter(item=>repeatedItems.indexOf(item) < 0);

    return diff;        
}

const foo = sym([1, 2, 3], [5, 2, 1, 4]); 
// -> [3,5,4]

const bar = sym([3, 6, 2, 5], [1, 5, 7], [3, 4, 6], [5, 2, 9, 8], [1]);

// -> [7, 4, 9, 8]
```

Answer in [Stackoverflow](https://stackoverflow.com/a/48705693/2323944)