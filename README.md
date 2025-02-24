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
#### JS - 9
-----------------------------------------------------------------------------------------





