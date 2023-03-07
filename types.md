# Basic Types in JavaScript

In JavaScript, the most basic types are: string, number, and boolean.

## Strings

Strings are used to represent textual data in JavaScript. They are enclosed in single or double quotes.

```javascript
const message = "Hello, World!";
```

## Numbers

Numbers are used to represent numeric data in JavaScript. They can be integers or decimals.

```javascript
const age = 25;
const price = 9.99;
```

## Booleans

Booleans are used to represent logical values in JavaScript. They can only have two possible values: `true` or `false`.

```javascript
const isAlive = true;
const isLoggedIn = false;
```

## Containers in JavaScript

There are a couple of very commonly used 'container' types in JavaScript. The first is the `array`;

### Arrays

An array is simply a list of items separated by a comma (,). The items guaranteed to be ordered, but they do not have to be unique.
In JavaScript, the values inside of an array can be of the same type or different types.

```javascript
const ages = [10, 15, 26, 86];
const businesses = ["Bentley Systems", "Apple", "HP", "Reebok"];
const houseNumbers = [101, "102A", "102B", 103];

// You can add items to an array with the 'push' method:

ages.push(99); // ages is now [10, 15, 26, 86, 99];

// you access items in an array using square brackets and the "index" of the item:
// an index is just the item's position in the array, starting at 0 (not 1!)
const firstValue = ages[0]; // 10
const secondValue = ages[1]; // 15

// you can update an item in a similar fashion:

ages[0] = 12; // first age in the array is now 12

// you can remove the last item off an array using the 'pop' keyword:

const lastValue = ages.pop(); // lastValue is 99, and ages is back to [10, 15, 26, 86];
```

### Objects in JavaScript

Objects in JavaScript are key:value pairs of data, with each pair's key and value separated by a colon (:).
Each pair is separated by a comma (,).

```javascript
// key: business name
// value: street address
const addressBook = {
  "Bentley Systems": "1601 Cherry St.",
  "Philadelphia City Hall": "1400 JFK Blvd.",
};

// you lookup values in an object using square brackets and a key which exists in the object:
addressBook["Bentley Systems"]; // "1601 Cherry St."

// you add items to an object using this square bracket syntax:
addressBook["Lincoln Financial Stadium"] = "One Lincoln Financial Field Way"; // now added to the addressBook

// you delete items from an object using the _delete_ keyword and the key of the item you want to delete:
delete addressBook["Bentley Systems"]; // it's now gone from the addressBook
```
