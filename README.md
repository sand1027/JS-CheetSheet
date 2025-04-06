# JS-CheetSheet
# 📚 JavaScript Methods Cheat Sheet

A complete reference of commonly used JavaScript methods for Arrays, Sets, Maps, and Strings — with code snippets and outputs. Perfect for interviews and day-to-day coding!

---

## 📌 Arrays (`[]`)

### ✅ Common Methods

#### `push()` / `pop()`
```js
const arr = [1, 2];
arr.push(3); // [1, 2, 3]
arr.pop();  // [1, 2]
```

#### `unshift()` / `shift()`
```js
const arr = [2, 3];
arr.unshift(1); // [1, 2, 3]
arr.shift();    // [2, 3]
```

#### `slice()`
```js
const arr = [1, 2, 3, 4];
arr.slice(1, 3); // [2, 3]
```

#### `splice()`
```js
const arr = [1, 2, 3];
arr.splice(1, 1); // [1, 3] (removes 2)
```

#### `concat()`
```js
[1, 2].concat([3, 4]); // [1, 2, 3, 4]
```

#### `indexOf()` / `includes()`
```js
const arr = [1, 2, 3];
arr.indexOf(2);    // 1
arr.includes(4);   // false
```

#### `reverse()` / `sort()`
```js
[1, 2, 3].reverse();     // [3, 2, 1]
[4, 2, 5].sort();        // [2, 4, 5] (lexical sort)
```

#### `join()`
```js
["a", "b"].join("-"); // "a-b"
```

#### `flat()`
```js
[1, [2, 3]].flat(); // [1, 2, 3]
```

#### `fill()`
```js
Array(3).fill(0); // [0, 0, 0]
```

### 🔁 Iteration Methods

#### `forEach()`
```js
[1, 2].forEach(x => console.log(x)); // 1 2
```

#### `map()`
```js
[1, 2].map(x => x * 2); // [2, 4]
```

#### `filter()`
```js
[1, 2, 3].filter(x => x > 1); // [2, 3]
```

#### `reduce()`
```js
[1, 2, 3].reduce((a, b) => a + b); // 6
```

#### `some()` / `every()`
```js
[1, 2, 3].some(x => x > 2);  // true
[1, 2, 3].every(x => x > 0); // true
```

#### `find()` / `findIndex()`
```js
[1, 2, 3].find(x => x > 1);      // 2
[1, 2, 3].findIndex(x => x > 1); // 1
```

### 🔄 Conversion Examples

#### Array ➡️ String
```js
const arr = [1, 2, 3];
const str = arr.join(",");
console.log(str); // "1,2,3"
```

#### String ➡️ Array
```js
const str = "1,2,3";
const arr = str.split(",");
console.log(arr); // ["1", "2", "3"]
```

#### Array ➡️ Set
```js
const arr = [1, 2, 2, 3];
const set = new Set(arr);
console.log(set); // Set(3) { 1, 2, 3 }
```

#### Set ➡️ Array
```js
const set = new Set([1, 2, 3]);
const arr = [...set];
console.log(arr); // [1, 2, 3]
```

#### Array ➡️ Linked List (custom example)
```js
function ListNode(val) {
  this.val = val;
  this.next = null;
}

function arrayToLinkedList(arr) {
  let dummy = new ListNode(0);
  let current = dummy;
  for (let num of arr) {
    current.next = new ListNode(num);
    current = current.next;
  }
  return dummy.next;
}

const list = arrayToLinkedList([1, 2, 3]);
console.log(list); // ListNode { val: 1, next: ListNode { val: 2, next: ListNode { val: 3, next: null } } }
```

#### Linked List ➡️ Array
```js
function linkedListToArray(head) {
  const result = [];
  while (head) {
    result.push(head.val);
    head = head.next;
  }
  return result;
}

const arr = linkedListToArray(list);
console.log(arr); // [1, 2, 3]
```

---

## 📌 Sets (`new Set()`)

```js
const set = new Set();
set.add(1);
set.add(2);
set.has(1);   // true
set.delete(2);
set.size;     // 1
```

#### Remove Duplicates from Array
```js
[...new Set([1, 2, 2, 3])]; // [1, 2, 3]
```

---

## 📌 Maps (`new Map()`)

```js
const map = new Map();
map.set("a", 1);
map.get("a");     // 1
map.has("a");     // true
map.delete("a");  // true
map.size;          // 0
```

#### Looping over Map
```js
for (let [key, value] of map) {
  console.log(key, value);
}
```

---

## 📌 Strings (`""`)

#### `charAt()` / `charCodeAt()`
```js
"abc".charAt(1);     // "b"
"abc".charCodeAt(0); // 97
```

#### `slice()` / `substring()` / `substr()`
```js
"hello".slice(1, 3);      // "el"
"hello".substring(1, 3);  // "el"
"hello".substr(1, 2);     // "el"
```

#### `includes()` / `startsWith()` / `endsWith()`
```js
"hello".includes("el");      // true
"hello".startsWith("he");    // true
"hello".endsWith("lo");      // true
```

#### `indexOf()` / `lastIndexOf()`
```js
"hello".indexOf("l");       // 2
"hello".lastIndexOf("l");   // 3
```

#### `replace()` / `replaceAll()`
```js
"hi there".replace("hi", "hello");       // "hello there"
"a-a-a".replaceAll("a", "b");           // "b-b-b"
```

#### `toUpperCase()` / `toLowerCase()`
```js
"abc".toUpperCase(); // "ABC"
"XYZ".toLowerCase(); // "xyz"
```

#### `trim()` / `split()` / `repeat()`
```js
"  abc  ".trim();       // "abc"
"a,b,c".split(",");     // ["a", "b", "c"]
"abc".repeat(3);         // "abcabcabc"
```

#### `padStart()` / `padEnd()`
```js
"5".padStart(3, "0"); // "005"
"5".padEnd(3, "0");   // "500"
```

---

### ✅ Tip:
Use these methods to manipulate data efficiently and solve problems in algorithms, DOM manipulation, and back-end logic.

---

### 💡 Contribution
Pull requests are welcome to add more examples and advanced tricks!

---

**Star** ⭐ this repo if it helped you!

