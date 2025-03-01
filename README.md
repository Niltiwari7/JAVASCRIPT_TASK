### JavaScript Notes chai and code

#### JS Lecture - 4 (let , const and var)

```javascript
    const accountId = 12345;
    let accountEmail = "nilesh@gmail.com";
    var accountPassword = "123456";
    let accountState;
    accountCity = "Uttar Pardesh";
    //accountId = 2;
    //console.log(accountId); TypeError : Assignment to constant variable.
    console.log(accountState); // undefined
    accountEmail = "nilesh@.com";
    accountPassword = "323232";
    accountCity = "Delhi";
    
    console.table([accountId,accountEmail,accountPassword,accountCity]);
```
- Note-: var is functional scope and let and const are block scope
------------------------------------------------------------
#### JS Lecture - 5 (Data types)
  ----------------------------------------------------------

| Data Type      | Example         | `typeof` Output  | Category        | Notes |
|---------------|----------------|-----------------|----------------|-------|
| **Number**    | `42`, `3.14`    | `"number"`      | Primitive      | Numeric values |
| **String**    | `"Hello"`       | `"string"`      | Primitive      | Textual data |
| **Boolean**   | `true`, `false` | `"boolean"`     | Primitive      | Logical values |
| **null**      | `null`          | `"object"`      | Primitive      | Historical bug in JavaScript |
| **undefined** | `let a;`        | `"undefined"`   | Primitive      | Uninitialized value |
| **Symbol**    | `Symbol('id')`  | `"symbol"`      | Primitive      | Unique identifier |
| **BigInt**    | `123n`          | `"bigint"`      | Primitive      | Used for large integers |
| **Object**    | `{}`, `[]`      | `"object"`      | Non-Primitive  | Collection of properties |
| **Array**     | `[1, 2, 3]`     | `"object"`      | Non-Primitive  | Special type of object |
| **Function**  | `function() {}` | `"function"`    | Non-Primitive  | Callable object |

---------------------------------------------------------------------------
#### JS Lecture - 6 (Data type conversion)
--------------------------------------------------------------------------
### **Conversion of Data to Number**  

| Expression           | `typeof` Output | Result | Notes |
|----------------------|---------------|--------|-----------------------------------|
| `Number("33abc")`   | `"number"`    | `NaN`  | Non-numeric strings return `NaN` |
| `NaN`               | `"number"`    | `NaN`  | `NaN` itself is of type `"number"` |
| `Number(null)`      | `"number"`    | `0`    | `null` converts to `0` |
| `Number(true)`      | `"number"`    | `1`    | `true` converts to `1` |
| `Number(false)`     | `"number"`    | `0`    | `false` converts to `0` |
| `Number("")`        | `"number"`    | `0`    | Empty string converts to `0` |
| `Number(undefined)` | `"number"`    | `NaN`  | `undefined` converts to `NaN` |

##### Truty value and falsy value
- Falsy values:

| Value            | Type       | Description |
|-----------------|-----------|-------------|
| `null`          | Null      | The keyword `null` represents the absence of any value. |
| `undefined`     | Undefined | The keyword `undefined` represents an uninitialized primitive value. |
| `false`         | Boolean   | The keyword `false`. |
| `NaN`          | Number    | `NaN` represents "Not-a-Number". |
| `0`            | Number    | The `Number` zero, including `0.0`, `0x0`, etc. |
| `-0`           | Number    | The `Number` negative zero, including `-0.0`, `-0x0`, etc. |
| `0n`           | BigInt    | The `BigInt` zero, including `0x0n`. Note that there is no negative `BigInt` zero — the negation of `0n` is `0n`. |
| `""`           | String    | An empty `string` value, including `''` and ``. |
| `document.all` | Object    | The only falsy object in JavaScript is the built-in `document.all`. |

- Truthy values: Any nonzero number, non-empty string, arrays ([]), objects ({}), and true.
Even an empty array [] or empty object {} is truthy.

----------------------------------------------------------------------------------------------
#### JS - 7 (Operator)
----------------------------------------------------------------------------------------------
##### **JavaScript Arithmetic Operations**

| Expression      | Result  | Explanation |
|---------------|--------|-------------|
| `1 + 2`      | `3`    | Simple addition of two numbers. |
| `2 ** 3`     | `8`    | Exponentiation: 2 raised to the power of 3. |
| `'3' + 2`    | `'32'` | String concatenation: `'3'` is treated as a string, so `2` is also converted to a string. |
| `'3' * 2`    | `6`    | Multiplication: JavaScript converts `'3'` to a number. |
| `'3' - 2`    | `1`    | Subtraction: JavaScript converts `'3'` to a number. |
| `'3' / 2`    | `1.5`  | Division: JavaScript converts `'3'` to a number. |
| `'3' % 2`    | `1`    | Modulus: JavaScript converts `'3'` to a number. |
| `3++`        | `4`    | Post-increment: Increases `3` by `1` (returns `4` in the next operation). |
| `3--`        | `2`    | Post-decrement: Decreases `3` by `1` (returns `2` in the next operation). |
| `'1' + 2 + 2` | `'122'` | `'1'` is a string, so `2 + 2` is concatenated, not added. |
| `1 + 2 + '2'` | `'32'` | `1 + 2` is `3`, then `'2'` is concatenated, resulting in `'32'`. |
--------------------------------------------------------------------------------------------------
#### JS - 8 (Comparison Output)
-------------------------------------------------------------------------------------------------


| Expression    | Output  | Explanation |
|--------------|--------|-------------|
| `"2" > 1`   | `true`  | `"2"` is converted to a number (`2 > 1`). |
| `"02" > 1`  | `true`  | `"02"` is converted to a number (`2 > 1`). |
| `null > 0`  | `false` | `null` is treated as `0` in comparisons but not in `>`. |
| `null == 0` | `false` | `null` is only equal to `undefined`, not `0`. |
| `null >= 0` | `true`  | `null` is treated as `0` in `>=`, so `0 >= 0` is `true`. |
| `undefined == 0` | `false` | `undefined` is only equal to `null`, not `0`. |
| `undefined > 0`  | `false` | `undefined` cannot be compared to numbers. |
| `undefined < 0`  | `false` | `undefined` cannot be compared to numbers. |
| `1 < 2 < 3`  | `true`  | `1 < 2` is `true` (`true` is `1`), then `1 < 3` is `true`. |
| `3 > 2 > 1`  | `false` | `3 > 2` is `true` (`true` is `1`), then `1 > 1` is `false`. |
|`null==undefined` | `true` | `Because both represent non-empty` |

-----------------------------------------------------------------------------------------
#### JS - 9 (Stack and Heap Memory)
-----------------------------------------------------------------------------------------

#### **1️⃣ Stack Memory (For Primitive Data Types)**
- Stores **primitive data types** (`Number`, `String`, `Boolean`, `null`, `undefined`, `Symbol`, `BigInt`).
- Stores values **directly**.
- When assigned to another variable, a **copy** is created.
- Changes in one variable **do not** affect the original.

🔹 **Example:**
```javascript
let myarr = "Nilesh Tiwari";
anotherArr = myarr;

console.log(myarr); // Nilesh Tiwari

anotherArr = "Nilesh is not good";

console.log(myarr); // Nilesh Tiwari (remains unchanged)
```
📌 *Since `myarr` is a primitive type (string), `anotherArr` gets a copy, so changes don’t affect the original.*

---

#### **2️⃣ Heap Memory (For Non-Primitive Data Types)**
- Stores **objects and arrays**.
- Stores values **by reference**.
- When assigned to another variable, the **reference (memory address) is copied**, not the value.
- Changes in one reference affect the original.

🔹 **Example:**
```javascript
let user = {
    name: "nilesh",
    age: 22,
};

user2 = user;  // Copying the reference
user.name = "Nilesh Tiwari";

console.log(user2.name); // Nilesh Tiwari
console.log(user.name); // Nilesh Tiwari
```
📌 *Since `user` is an object (stored in Heap), both `user` and `user2` refer to the same memory location. Changing `user.name` affects `user2.name` too.*

---

### **🔹 Key Takeaways**
✅ **Primitive Types → Stack Memory (Copying values, independent changes).**  
✅ **Non-Primitive Types → Heap Memory (Copying references, changes affect all references).**  

-------------------------------------------------------------------------------------
JS - 11 (String in JavaScript)
-------------------------------------------------------------------------------------

### 📌 **JavaScript Strings & Methods – Quick Notes**  

#### **1️⃣ String Declaration**
- Strings can be declared using **`""` (double quotes), `''` (single quotes), or template literals ` (backticks).**
```javascript
const name = "Nilesh-tiwari";
const repoCount = 50;

// Modern way (Template Literals)
console.log(`I am ${name} and my repo count is ${repoCount}`);
```
📌 *Template literals allow embedding variables inside a string using `${}`.*

---

#### **2️⃣ String Properties & Methods**
##### **🔹 Basic String Properties**
```javascript
const s = new String("Nilesh");
console.log(s.length); // 6
```
📌 *The `length` property returns the number of characters in a string.*

---

##### **🔹 String Case Conversion**
```javascript
console.log(s.toUpperCase()); // "NILESH"
console.log(s.toLowerCase()); // "nilesh"
```
📌 *Converts a string to uppercase or lowercase.*

---

##### **🔹 Character Access**
```javascript
console.log(s.charAt(2)); // 'l' (3rd character)
console.log(s.indexOf("h")); // 5 (Position of 'h')
```
📌 *`charAt(index)`: Returns the character at a specific index.*  
📌 *`indexOf("char")`: Returns the first occurrence index of the character.*

---

##### **🔹 Extracting Substrings**
```javascript
const newString = s.substring(0, 4); // "Nile"
console.log(newString);

const anotherString = "Nilesh Tiwari";
console.log(anotherString.slice(0, 4));  // "Nile"
console.log(anotherString.slice(0, -4)); // "Nilesh Ti"
```
📌 *`substring(start, end)`: Extracts a portion of a string (excluding end index).*  
📌 *`slice(start, end)`: Supports negative indexing.*

---

##### **🔹 Trimming Whitespace**
```javascript
const newStr1 = "    Nilesh    ";
console.log(newStr1.trim()); // "Nilesh"
```
📌 *`trim()` removes leading and trailing spaces.*

---

##### **🔹 Replacing Characters in Strings**
```javascript
const url = "https://nilesh.com/nilesh%20tiwari";
console.log(url.replace("%20", "-")); // "https://nilesh.com/nilesh-tiwari"
```
📌 *`replace("old", "new")` replaces the first occurrence of a value.*

---

##### **🔹 Checking Substring Presence**
```javascript
console.log(url.includes("nilesh")); // true
```
📌 *`includes("substring")` checks if a string contains a specific text.*

---

##### **🔹 Splitting Strings into Arrays**
```javascript
console.log("Nilesh Tiwari".split(" ")); // [ 'Nilesh', 'Tiwari' ]
```
📌 *`split("delimiter")` converts a string into an array based on the delimiter.*

---

### **🔹 Key Takeaways**
✅ **Template Literals (`${}`) → Modern way for string interpolation.**  
✅ **`toUpperCase()`, `toLowerCase()` → Change case.**  
✅ **`charAt()`, `indexOf()` → Access characters.**  
✅ **`substring()`, `slice()` → Extract parts of a string.**  
✅ **`trim()` → Remove extra spaces.**  
✅ **`replace()` → Replace characters in a string.**  
✅ **`includes()` → Check for substring existence.**  
✅ **`split()` → Convert string to array.**  

------------------------------------------------------------------------------------
JS - 12 (Number and Maths in JS)
------------------------------------------------------------------------------------
### 📌 **JavaScript Number Methods – Quick Notes**  

#### **1️⃣ Converting Numbers to Strings**
```javascript
const score = 100;
console.log(score.toString()); // "100"
```
📌 *`toString()` converts a number into a string.*

---

#### **2️⃣ Formatting Numbers with Decimals**
```javascript
console.log(score.toFixed(1)); // "100.0"
```
📌 *`toFixed(decimalPlaces)` formats the number with a fixed number of decimal places.*  
📌 *Returns a string.*

---

#### **3️⃣ Precision Formatting**
```javascript
const otherNumber = 23.456;
console.log(otherNumber.toPrecision(3)); // "23.5"
```
📌 *`toPrecision(n)` rounds a number to `n` significant digits and returns a string.*  

---

#### **4️⃣ Formatting Numbers with Locale**
```javascript
const hundred = 1000000;
console.log(hundred.toLocaleString()); // "1,000,000"
console.log(hundred.toLocaleString("en-IN")); // "10,00,000"
```
📌 *`toLocaleString()` formats numbers with commas based on the given locale.*  
📌 `"en-US"` (default) → **1,000,000**  
📌 `"en-IN"` (Indian system) → **10,00,000**  

---

### **🔹 Key Takeaways**
✅ **`toString()` → Convert number to string.**  
✅ **`toFixed(n)` → Format with `n` decimal places.**  
✅ **`toPrecision(n)` → Round to `n` significant digits.**  
✅ **`toLocaleString("locale")` → Format numbers with commas based on locale.**  

]### 📌 **JavaScript Math Methods – Quick Notes**  

#### **1️⃣ Absolute Value**
```javascript
console.log(Math.abs(-4)); // 4
```
📌 *`Math.abs(x)` returns the absolute (positive) value of a number.*

---

#### **2️⃣ Rounding Numbers**
```javascript
console.log(Math.round(4.3)); // 4
console.log(Math.round(4.7)); // 5
```
📌 *`Math.round(x)` rounds a number to the nearest integer.*

---

#### **3️⃣ Ceiling & Floor**
```javascript
console.log(Math.ceil(4.3)); // 5
console.log(Math.floor(4.9)); // 4
```
📌 *`Math.ceil(x)` rounds **UP** to the nearest integer.*  
📌 *`Math.floor(x)` rounds **DOWN** to the nearest integer.*

---

#### **4️⃣ Finding Minimum & Maximum**
```javascript
console.log(Math.min(4, 3, 2, 1)); // 1
console.log(Math.max(4, 3, 2, 1)); // 4
```
📌 *`Math.min()` and `Math.max()` return the smallest and largest number in a set.*

---

#### **5️⃣ Generating Random Numbers**
```javascript
console.log(Math.random()); // 0 to 1
console.log(Math.random() * 10); // 0 to 10
console.log(Math.random() * 10 + 1); // 1 to 10
```
📌 *`Math.random()` generates a random decimal between `0` and `1`.*  
📌 *Multiply by 10 to get a random number from `0 to 10`.*  
📌 *Adding `1` ensures a range from `1 to 10`.*

---

#### **6️⃣ Generating Random Numbers Within a Range**
```javascript
const min = 10;
const max = 20;
console.log(Math.floor(Math.random() * (max - min + 1) + min)); // 10 to 20
```
📌 *Formula for a random integer between `min` and `max`:*  
💡 `Math.floor(Math.random() * (max - min + 1) + min)`

---

### **🔹 Key Takeaways**
✅ **`Math.abs(x)`** → Returns absolute value.  
✅ **`Math.round(x)`** → Rounds to the nearest integer.  
✅ **`Math.ceil(x)`** → Rounds up.  
✅ **`Math.floor(x)`** → Rounds down.  
✅ **`Math.min(x, y, ...z)`** → Returns the smallest number.  
✅ **`Math.max(x, y, ...z)`** → Returns the largest number.  
✅ **`Math.random()`** → Generates a random number between `0-1`.  
✅ **Formula for range:** `Math.floor(Math.random() * (max - min + 1) + min)`  

---------------------------------------------------------------------------------
JS - 13 (Dates)
---------------------------------------------------------------------------------
### 📌 **JavaScript Date Methods – Quick Notes**  

JavaScript provides the `Date` object to work with dates and times.  

---

### **1️⃣ Creating a Date Object**
```javascript
const now = new Date();
console.log(now); // Current date and time
```
📌 *Creates a new `Date` object with the current date and time.*

---

### **2️⃣ Creating a Specific Date**
```javascript
const specificDate = new Date(2024, 1, 26); 
console.log(specificDate); // Mon Feb 26 2024
```
📌 *Month starts from **0 (January) to 11 (December)**.*

```javascript
const customDate = new Date("2024-02-26");
console.log(customDate); // Mon Feb 26 2024
```
📌 *You can pass a string in `"YYYY-MM-DD"` format.*

---

### **3️⃣ Getting Date Components**
```javascript
const date = new Date();

console.log(date.getFullYear()); // 2024
console.log(date.getMonth()); // 1 (February, as it's 0-based)
console.log(date.getDate()); // 26 (Day of the month)
console.log(date.getDay()); // 1 (Monday, where Sunday is 0)
console.log(date.getHours()); // Current hour
console.log(date.getMinutes()); // Current minute
console.log(date.getSeconds()); // Current second
console.log(date.getMilliseconds()); // Current millisecond
```
📌 *Extracts specific parts of the date and time.*

---

### **4️⃣ Setting Date Components**
```javascript
const newDate = new Date();

newDate.setFullYear(2025);
newDate.setMonth(5); // June (0-based index)
newDate.setDate(10);
newDate.setHours(15);

console.log(newDate); // Tue Jun 10 2025 15:00:00
```
📌 *Allows modifying date values.*

---

### **5️⃣ Formatting Dates**
```javascript
const date = new Date();
console.log(date.toDateString()); // "Mon Feb 26 2024"
console.log(date.toTimeString()); // "14:35:27 GMT+0530 (IST)"
console.log(date.toISOString()); // "2024-02-26T09:05:27.451Z"
console.log(date.toLocaleString("en-US")); // "2/26/2024, 2:35:27 PM"
console.log(date.toLocaleDateString()); // "2/26/2024"
console.log(date.toLocaleTimeString()); // "2:35:27 PM"
```
📌 *Formats date and time in different styles.*

---

### **6️⃣ Comparing Dates**
```javascript
const date1 = new Date("2024-02-26");
const date2 = new Date("2024-03-01");

console.log(date1 > date2); // false
console.log(date1 < date2); // true
console.log(date1.getTime() === date2.getTime()); // false
```
📌 *Dates can be compared using operators (`<`, `>`, `===`). Convert them to milliseconds using `.getTime()` for accuracy.*

---

### **7️⃣ Date Difference in Days**
```javascript
const start = new Date("2024-02-20");
const end = new Date("2024-02-26");

const diffInTime = end.getTime() - start.getTime();
const diffInDays = diffInTime / (1000 * 60 * 60 * 24);

console.log(diffInDays); // 6
```
📌 *Finds the difference between two dates in days.*

---

### **🔹 Key Takeaways**
✅ `new Date()` → Creates a new date object.  
✅ `getFullYear(), getMonth(), getDate(), getDay()` → Extracts date values.  
✅ `setFullYear(), setMonth(), setDate(), setHours()` → Modifies date values.  
✅ `toDateString(), toLocaleString(), toISOString()` → Formats date/time.  
✅ `date1 > date2` → Compares dates.  
✅ `getTime()` → Converts date to milliseconds for comparison.  
✅ **Formula for Date Difference:**  
💡 `(date2.getTime() - date1.getTime()) / (1000 * 60 * 60 * 24)`

-------------------------------------------------------------------------------------
JS - 14 (Array)
-------------------------------------------------------------------------------------

### 📌 **JavaScript Arrays – Quick Notes**  

JavaScript arrays allow storing multiple values in a single variable.  

---

### **1️⃣ Creating an Array**
```javascript
const myarr = [1, 2, 3, 4, 5];
const myarr1 = new Array(1, 2, 3, 4, 5);

console.log(myarr); // [1, 2, 3, 4, 5]
```
📌 *Arrays can be created using `[]` (recommended) or `new Array()`.*

---

### **2️⃣ Accessing Elements**
```javascript
console.log(myarr[2]); // 3
console.log(myarr.length); // 5
```
📌 *Use index (`0-based`) to access elements. `.length` returns the total number of elements.*

---

### **3️⃣ Checking If a Variable is an Array**
```javascript
console.log(Array.isArray(myarr)); // true
```
📌 *Checks if a variable is an array.*

---

### **4️⃣ Converting Array to String**
```javascript
console.log(myarr.toString()); // "1,2,3,4,5"
console.log(myarr.join("-")); // "1-2-3-4-5"
```
📌 *`.toString()` converts an array to a comma-separated string. `.join()` allows custom separators.*

---

### **5️⃣ Adding and Removing Elements**
```javascript
const myarr2 = [1, 2, 3, 4, 5];

myarr2.push(6);  // [1, 2, 3, 4, 5, 6]  ➝ Add at end
myarr2.pop();    // [1, 2, 3, 4, 5]  ➝ Remove from end

myarr2.unshift(0); // [0, 1, 2, 3, 4, 5] ➝ Add at beginning
myarr2.shift();  // [1, 2, 3, 4, 5] ➝ Remove from beginning
```
📌 *Use `push()` & `pop()` for end operations, `unshift()` & `shift()` for start operations.*

---

### **6️⃣ Searching in Arrays**
```javascript
console.log(myarr2.includes(4)); // true
console.log(myarr2.indexOf(4)); // 3
```
📌 *`.includes()` checks if a value exists, `.indexOf()` returns the index of the value (or `-1` if not found).*

---

### **7️⃣ Combining Arrays**
```javascript
const newarr = myarr2.concat(myarr);
console.log(newarr); // [1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
```
📌 *`.concat()` merges two arrays without modifying the original arrays.*

---

### **8️⃣ Extracting Parts of an Array**
```javascript
console.log(myarr2.slice(1, 3)); // [2, 3]
```
📌 *`.slice(start, end)` extracts elements from an array (returns a new array, doesn't modify the original).*

---

### **9️⃣ Removing/Adding Elements in an Array**
```javascript
console.log(myarr2.splice(1, 3)); // [2, 3, 4]
console.log(myarr2); // [1, 5]
```
📌 *`.splice(start, deleteCount, item1, item2, ... )` removes/replaces elements and **modifies** the original array.*

---

### **🔹 Key Difference: `slice()` vs `splice()`**
| Method  | Returns New Array? | Modifies Original Array? | Purpose |
|---------|-------------------|------------------------|----------|
| `slice(start, end)` | ✅ Yes | ❌ No | Extracts part of an array |
| `splice(start, deleteCount, ...items)` | ❌ No | ✅ Yes | Removes/replaces elements |

---

### 📌 **Advanced JavaScript Array Methods – Quick Notes**  

JavaScript provides various array methods to manipulate and transform arrays effectively.  

---

### **1️⃣ `slice()` – Extracting Elements Without Modification**
```javascript
const myarr = [1,2,3,4,5];

console.log(myarr.slice(1));    // [2, 3, 4, 5]
console.log(myarr.slice(1, 3)); // [2, 3]
```
📌 *`slice(start, end)` extracts elements without modifying the original array.*  
✅ Returns a **new array**.  
✅ `start` is included, `end` is excluded.

---

### **2️⃣ `splice()` – Removing/Modifying Elements**
```javascript
console.log(myarr.splice(1, 3)); // [2, 3, 4]
console.log(myarr);              // [1, 5]
```
📌 *`splice(start, deleteCount, item1, item2, ...)` removes/replaces elements and modifies the original array.*  
✅ **Changes** the original array.  
✅ Can **insert** or **replace** elements if additional items are provided.

---

### **3️⃣ `flat()` – Flattening Nested Arrays**
```javascript
const myarr1 = [1,2,3,4,[2,3,4],[3,4],[4,5,[5]]];
console.log(myarr1.flat()); 
// [ 1, 2, 3, 4, 2, 3, 4, 3, 4, 4, 5, [5] ]
```
📌 *`flat(depth)` flattens a nested array structure.*  
✅ By default, `flat()` works at **depth = 1**.  
✅ Use `flat(Infinity)` to completely flatten deeply nested arrays.

---

### **4️⃣ `Array.from()` – Converting Strings & Objects to Arrays**
```javascript
const str = "Nilesh";
const myarr2 = Array.from(str);
console.log(myarr2); // [ 'N', 'i', 'l', 'e', 's', 'h' ]
```
📌 *`Array.from(iterable)` creates an array from any iterable, such as strings or NodeLists.*  
✅ Useful for converting strings, sets, or DOM elements into arrays.

---

### **5️⃣ `Array.of()` – Creating an Array from Values**
```javascript
const scores1 = 300;
const scores2 = 200;
const scores3 = 100;

const myarr3 = Array.of(scores1, scores2, scores3);
console.log(myarr3); // [ 300, 200, 100 ]
```
📌 *`Array.of(element1, element2, ...)` creates an array from given values.*  
✅ Unlike `new Array()`, it ensures proper handling of a **single numeric argument**.  

---

### **🔹 Key Differences**
| Method | Purpose | Modifies Original Array? | Returns New Array? |
|--------|---------|--------------------------|----------------------|
| `slice()` | Extracts elements | ❌ No | ✅ Yes |
| `splice()` | Removes/Replaces elements | ✅ Yes | ❌ No |
| `flat()` | Flattens nested arrays | ❌ No | ✅ Yes |
| `Array.from()` | Converts an iterable to an array | ❌ No | ✅ Yes |
| `Array.of()` | Creates an array from values | ❌ No | ✅ Yes |

---

### **🔹 Summary**
✅ Use `slice()` when you want to **extract** elements **without modifying** the original array.  
✅ Use `splice()` when you want to **remove/replace** elements **and modify** the original array.  
✅ Use `flat()` to **flatten** nested arrays into a single-level array.  
✅ Use `Array.from()` to **convert** strings, sets, or NodeLists into arrays.  
✅ Use `Array.of()` to **create an array from values** safely.  


-----------------------------------------------------------------------------------
JS - 15 (Object)
----------------------------------------------------------------------------------
### 📌 **JavaScript Objects – Quick Notes**  

JavaScript objects are collections of key-value pairs used to store structured data.

---

### **1️⃣ Creating an Object – Object Literals**  
```javascript
const user = {
    name: "Nilesh",
    age: 22,
};
```
📌 *An object is created using curly braces `{}` with key-value pairs.*  
✅ Keys are **strings** (or symbols).  
✅ Values can be **any data type** (strings, numbers, functions, etc.).  

---

### **2️⃣ Accessing Object Properties**  
```javascript
console.log(user.name);   // nilesh
console.log(user["name"]); // nilesh
```
📌 *There are two ways to access object properties:*  
✅ **Dot Notation:** `user.name` (Most common)  
✅ **Bracket Notation:** `user["name"]` (Useful when the key is dynamic)  

---

### **3️⃣ Modifying Object Properties**
```javascript
user.name = "Nilesh Tiwari";
console.log(user.name); // Nilesh Tiwari
```
📌 *Objects are mutable, so properties can be updated directly.*

---

### **4️⃣ Object Methods for Keys & Values**
```javascript
console.log(Object.keys(user));   // [ 'name', 'age' ]
console.log(Object.values(user)); // [ 'Nilesh Tiwari', 22 ]
console.log(Object.entries(user)); // [ ['name', 'Nilesh Tiwari'], ['age', 22] ]
```
📌 `Object.keys(obj)` → Returns an **array of keys**.  
📌 `Object.values(obj)` → Returns an **array of values**.  
📌 `Object.entries(obj)` → Returns an **array of key-value pairs**.  

---

### **5️⃣ Adding Methods to an Object**
```javascript
user.greetings = function(){
    console.log("Hello");
}

user.greetings(); // Hello
```
📌 *Functions can be added as properties inside objects, turning them into methods.*

---

### **🔹 Summary Table**
| Feature | Syntax | Example |
|---------|--------|---------|
| Object Creation | `{}` | `const user = { name: "Nilesh", age: 22 }` |
| Accessing Properties | `.` or `[]` | `user.name` or `user["name"]` |
| Modifying Properties | `=` | `user.name = "Nilesh Tiwari"` |
| Get Keys | `Object.keys(obj)` | `['name', 'age']` |
| Get Values | `Object.values(obj)` | `['Nilesh Tiwari', 22]` |
| Get Entries | `Object.entries(obj)` | `[ ['name', 'Nilesh Tiwari'], ['age', 22] ]` |
| Add Method | `obj.method = function(){}` | `user.greetings = function(){ console.log("Hello"); }` |

---

### **🔹 Summary**
✅ Use **object literals** `{}` to create objects.  
✅ Access object properties using **dot notation** or **bracket notation**.  
✅ Modify object properties **directly**.  
✅ Use **`Object.keys()`, `Object.values()`, and `Object.entries()`** to extract information.  
✅ Add **functions** inside objects to define **methods**.  

--------------------------------------------------------------------------
Js - 18
---

## **Object Destructuring in JavaScript**

### **What is Object Destructuring?**
Object destructuring is a convenient way to extract values from an object and store them in variables.

Instead of accessing properties using dot notation:

```javascript
const course = {
    coursename: "Js is love",
    price: "999",
    courseInstructor: "Nilesh"
};

console.log(course.coursename);  // "Js is love"
console.log(course.price);        // "999"
console.log(course.courseInstructor);  // "Nilesh"
```

We can **destructure** the object like this:

```javascript
const { coursename, price, courseInstructor } = course;

console.log(coursename);  // "Js is love"
console.log(price);        // "999"
console.log(courseInstructor);  // "Nilesh"
```

---

### **Example: Using Object Destructuring in an Array of Objects**
When we have multiple objects inside an array, we can destructure them inside a loop or while mapping.

```javascript
const courses = [
    {
        coursename: "Js is love",
        price: "999",
        courseInstructor: "Nilesh"
    },
    {
        coursename: "React Mastery",
        price: "1499",
        courseInstructor: "Sumit"
    },
    {
        coursename: "Node.js Essentials",
        price: "1299",
        courseInstructor: "Aman"
    }
];

// Destructuring inside a loop
courses.forEach(({ coursename, price, courseInstructor }) => {
    console.log(`Course: ${coursename}, Price: ${price}, Instructor: ${courseInstructor}`);
});
```

**Output:**
```
Course: Js is love, Price: 999, Instructor: Nilesh
Course: React Mastery, Price: 1499, Instructor: Sumit
Course: Node.js Essentials, Price: 1299, Instructor: Aman
```

---

### **Benefits of Object Destructuring**
✅ **Cleaner Code:** Reduces redundant property access (`obj.property`).  
✅ **Improves Readability:** Easy to understand and use.  
✅ **Extracts Only What You Need:** No need to store the entire object in a variable.  

---
--------------------------------------------------------------------
JS - 19 (Function)
-------------------------------------------------------------------
# **JavaScript - Functions & Rest Parameters (`...`)**

## **1. Understanding the Code**
### **Example: Function with Rest Parameter**
```javascript
function calculatePrice(...num1) {
  return num1;
}

console.log(calculatePrice(3, 2, 3));
```
### **Output:**
```
[3, 2, 3]
```

---

## **2. Key Concepts**
### **A. Function Basics**
- A function in JavaScript is a reusable block of code that performs a specific task.
- It is declared using the `function` keyword.

### **B. Rest Parameters (`...`)**
- The `...` (spread/rest operator) **gathers multiple arguments** into an **array**.
- In the above function, `...num1` collects all arguments passed into `calculatePrice()` and stores them in an array.

---

## **3. Explanation**
```javascript
function calculatePrice(...num1) {
  return num1;  // num1 is an array
}
```
- Here, `...num1` gathers all arguments passed into the function and stores them in `num1`.
- The function then **returns** `num1`, which is an array.

### **Example Execution**
```javascript
console.log(calculatePrice(3, 2, 3));
```
- `3, 2, 3` are passed as arguments.
- The rest parameter (`...num1`) collects them into an array: `[3, 2, 3]`.
- The function **returns** `[3, 2, 3]`.

---

## **4. Practical Use Case**
Rest parameters are useful when a function needs to handle **an unknown number of arguments**.

### **Example: Sum of All Numbers**
```javascript
function sumAll(...numbers) {
  return numbers.reduce((acc, curr) => acc + curr, 0);
}

console.log(sumAll(10, 20, 30, 40)); // Output: 100
```
- The function accepts **any number of arguments**.
- It **adds all numbers together** using `.reduce()`.

---

## **5. Key Takeaways**
✅ **Rest Parameter (`...`) gathers multiple arguments into an array.**  
✅ **Functions can handle flexible arguments dynamically.**  
✅ **Useful for operations like summing numbers, merging values, or collecting user inputs.**  

-----------------------------------------------------------------------------------
JS - 21 (Global and local scope)
----------------------------------------------------------------------------------

# **JavaScript - Global and Local Scope**  

## **1. What is Scope in JavaScript?**  
Scope in JavaScript defines **where** variables and functions are accessible in your code. There are two main types:  

1️⃣ **Global Scope** → Accessible anywhere in the script.  
2️⃣ **Local Scope** → Accessible only inside a specific function or block.  

---

## **2. Global Scope**  
A variable declared **outside** any function or block is **global** and can be accessed anywhere in the script.

### **Example of Global Scope**  
```javascript
let globalVar = "I am a global variable";

function printGlobal() {
    console.log(globalVar); // Accessible inside function
}

printGlobal();  // Output: I am a global variable
console.log(globalVar);  // Output: I am a global variable
```

📌 **Global variables can be accessed from anywhere in the script!**  

---

## **3. Local Scope (Function Scope)**  
Variables declared **inside a function** are local to that function and **cannot be accessed outside**.

### **Example of Local Scope**  
```javascript
function localExample() {
    let localVar = "I am a local variable";
    console.log(localVar);  // Output: I am a local variable
}

localExample();
console.log(localVar);  // ❌ Error: localVar is not defined
```

📌 **Local variables exist only inside the function. They are destroyed after the function runs.**  

---

## **4. Block Scope (`let` & `const`)**  
Variables declared with `let` or `const` inside `{}` **are restricted to that block**.

### **Example of Block Scope**  
```javascript
{
    let blockVar = "I exist only inside this block";
    console.log(blockVar); // ✅ Works inside block
}

console.log(blockVar); // ❌ Error: blockVar is not defined
```
📌 **Block-scoped variables exist only within `{}` (if-else, loops, etc.).**  

---

## **5. Difference Between `var`, `let`, and `const` Scope**  

| Variable Type | Scope Type | Can be Re-declared? | Block Scope? |
|--------------|-----------|------------------|--------------|
| `var`       | Function Scope | ✅ Yes  | ❌ No |
| `let`       | Block Scope  | ❌ No | ✅ Yes |
| `const`     | Block Scope  | ❌ No | ✅ Yes |

### **Example of `var` vs `let` Scope**
```javascript
function testVar() {
    if (true) {
        var a = 10;  // Function-scoped
        let b = 20;  // Block-scoped
    }
    console.log(a); // ✅ Works (var is function-scoped)
    console.log(b); // ❌ Error (b is block-scoped)
}

testVar();
```

---

## **6. Nested Scope (Lexical Scope)**
Inner functions **can access** outer function variables.

```javascript
function outerFunction() {
    let outerVar = "I'm outside!";

    function innerFunction() {
        console.log(outerVar); // ✅ Accessible inside
    }

    innerFunction();
}

outerFunction(); // Output: I'm outside!
```
📌 **Inner functions can access outer function variables, but not vice versa.**

---

## **7. Summary**  
✅ **Global Scope:** Accessible anywhere.  
✅ **Local Scope:** Exists only inside a function.  
✅ **Block Scope (`let` & `const`)**: Exists only inside `{}`.  
✅ **Nested Scope:** Inner functions can access outer variables.  
✅ **Use `let` and `const` instead of `var`** to avoid accidental reassignments.

---------------------------------------------------------------------------------
JS - 22 (hoisting and closure)
----------------------------------------------------------------------------------
# **JavaScript - Hoisting and Closure**  

## **1. Hoisting in JavaScript**  

### **What is Hoisting?**  
Hoisting is a JavaScript mechanism where **function and variable declarations are moved to the top of their scope** before the code executes.  

---

### **Example 1: Hoisting with `var`**
```javascript
console.log(a); // Output: undefined
var a = 10;
console.log(a); // Output: 10
```
📌 **Why?**  
- JavaScript **hoists** the `var a;` declaration to the top but does **not** hoist its value.
- So, `a` exists but is **undefined** before assignment.

---

### **Example 2: Hoisting with `let` and `const`**
```javascript
console.log(b); // ❌ Error: Cannot access 'b' before initialization
let b = 20;
```
📌 **Why?**  
- `let` and `const` are hoisted but are **not initialized**. They exist in a **Temporal Dead Zone (TDZ)** until assigned a value.

---

### **Example 3: Hoisting with Functions**
```javascript
greet(); // ✅ Works! Output: Hello!

function greet() {
    console.log("Hello!");
}
```
📌 **Why?**  
- **Function declarations** are fully hoisted, meaning the function can be called before it's defined.

#### **Function Expressions are NOT Hoisted!**
```javascript
hello(); // ❌ Error: Cannot access 'hello' before initialization
const hello = function() {
    console.log("Hi!");
};
```
📌 **Why?**  
- **Function expressions (assigned to variables)** are hoisted but are in a **TDZ** like `let` and `const`.

---

## **2. Closures in JavaScript**  

### **What is a Closure?**  
A closure is a function that **remembers** the variables from its outer scope even after the outer function has finished executing.

---

### **Example 1: Simple Closure**
```javascript
function outerFunction() {
    let outerVar = "I am from outer function";

    function innerFunction() {
        console.log(outerVar); // ✅ Can access outerVar
    }

    return innerFunction;
}

const myClosure = outerFunction(); 
myClosure(); // Output: I am from outer function
```
📌 **Why?**  
- `innerFunction` **remembers** `outerVar` even after `outerFunction` has finished execution.

---

### **Example 2: Real-World Closure - Counter**
```javascript
function createCounter() {
    let count = 0; // Private variable

    return function () {
        count++;
        console.log(count);
    };
}

const counter = createCounter();
counter(); // Output: 1
counter(); // Output: 2
counter(); // Output: 3
```
📌 **Why?**  
- `count` is **not directly accessible**, but the returned function **remembers and modifies it**.

---

### **3. Key Differences Between Hoisting and Closure**
| Feature  | Hoisting  | Closure  |
|----------|----------|----------|
| **Definition** | Moving variable & function declarations to the top of the scope | Functions remembering their outer scope |
| **Example** | Accessing a variable before it's declared | Keeping data private in a function |
| **Works With** | `var`, `let`, `const`, functions | Nested functions |

---

### **4. Summary**
✅ **Hoisting** moves declarations to the top but does **not** hoist values.  
✅ **Function declarations are hoisted, but function expressions are not.**  
✅ **Closures allow functions to remember variables even after their parent function executes.**  
✅ **Closures are useful for creating private variables and encapsulation.**  

----------------------------------------------------------------------------------
JS - 23 (this and arrow function)
----------------------------------------------------------------------------------
# **JavaScript - `this` and Arrow Functions**  

## **1. Understanding `this` in JavaScript**  
The `this` keyword refers to **the object that is currently executing the function**. However, its value depends on **how** the function is called.  

### **1.1 `this` in Global Scope**  
```javascript
console.log(this); 
// In a browser, `this` refers to the `window` object.
// In Node.js, `this` refers to an empty object `{}`.
```

---

### **1.2 `this` in an Object Method**  
```javascript
const person = {
    name: "Nilesh",
    greet: function () {
        console.log(this.name); // Refers to 'person' object
    }
};

person.greet(); // Output: Nilesh
```
📌 **Why?**  
- Here, `this` refers to the `person` object because `greet` is called **on** `person`.

---

### **1.3 `this` in a Function (Default Binding - Global Scope)**
```javascript
function show() {
    console.log(this);
}
show(); // In strict mode: `undefined`, Otherwise: `window` (in browsers)
```
📌 **Why?**  
- In non-strict mode, `this` refers to the `window` object in browsers.
- In strict mode (`"use strict";`), `this` is `undefined`.

---

### **1.4 `this` in a Constructor Function**
```javascript
function Car(name) {
    this.name = name;
}

const myCar = new Car("Volkswagen");
console.log(myCar.name); // Output: Volkswagen
```
📌 **Why?**  
- `this` refers to the new object created by `new Car("Volkswagen")`.

---

### **1.5 `this` Inside an Event Listener**
```javascript
const button = document.querySelector("button");
button.addEventListener("click", function () {
    console.log(this); // `this` refers to the button element
});
```
📌 **Why?**  
- In an event listener, `this` refers to the element that triggered the event.

---

## **2. Arrow Functions and `this`**  
Arrow functions behave **differently** with `this`. They do **not** bind their own `this` but inherit it from the surrounding scope.

### **2.1 Arrow Function Inside an Object**
```javascript
const person = {
    name: "Nilesh",
    greet: () => {
        console.log(this.name);
    }
};

person.greet(); // Output: undefined
```
📌 **Why?**  
- Arrow functions **do not** have their own `this`.  
- `this` is inherited from the global scope (`window`), which has no `name` property.

---

### **2.2 Arrow Function Inside a Method**
```javascript
const person = {
    name: "Nilesh",
    greet: function () {
        let sayHello = () => {
            console.log(this.name); // ✅ Inherits `this` from `greet`
        };
        sayHello();
    }
};

person.greet(); // Output: Nilesh
```
📌 **Why?**  
- `sayHello` is an arrow function, so it **inherits `this` from `greet`**, which belongs to `person`.

---

### **2.3 Arrow Functions in Callbacks**
```javascript
const numbers = [1, 2, 3];
numbers.forEach((num) => console.log(num)); // ✅ Works fine!
```
📌 **Why?**  
- Arrow functions work well in callbacks as they don’t bind `this`.

---

## **3. Key Differences Between Regular Functions and Arrow Functions**
| Feature | Regular Function | Arrow Function |
|---------|----------------|---------------|
| **`this` Binding** | Depends on how function is called | Inherits `this` from surrounding scope |
| **Object Method** | `this` refers to the calling object | `this` refers to global scope (not the object) |
| **Constructor Function** | Can be used as a constructor (`new` keyword) | ❌ Cannot be used as a constructor |
| **Event Listeners** | `this` refers to the element | `this` refers to outer scope (not element) |

---

## **4. Summary**
✅ **`this` refers to the object that calls the function.**  
✅ **Arrow functions don’t have their own `this`; they inherit it from their surrounding scope.**  
✅ **Use regular functions inside objects if `this` is needed.**  
✅ **Use arrow functions for callbacks, promises, and `map`, `filter`, `reduce`.** 
-----------------------------------------------------------------------------------

----------------------------------------------------------------------------------
