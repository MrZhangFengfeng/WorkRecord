### 废话不多说，又被测试找出bug了。
- - -
记录isNaN的返回值。

    isNaN(NaN);       // true
    isNaN(undefined); // true
    isNaN({});        // true

    isNaN(true);      // false
    isNaN(null);      // false
    isNaN(37);        // false

    // strings
    isNaN('37');      // false: "37" is converted to the number 37 which is not NaN
    isNaN('37.37');   // false: "37.37" is converted to the number 37.37 which is not NaN
    isNaN('123ABC');  // true:  parseInt("123ABC") is 123 but Number("123ABC") is NaN
    isNaN('');        // false: the empty string is converted to 0 which is not NaN
    isNaN(' ');       // false: a string with spaces is converted to 0 which is not NaN

    // dates
    isNaN(new Date());                // false
    isNaN(new Date().toString());     // true

    isNaN('blabla');   // true: "blabla" is converted to a number. if Parsing this as a number fails and returns NaN
    
    
- - -

## `Number.isNaN` 和 `isNaN`不一样！！

`Number.isNaN` 和 `isNaN` 有何区别呢？
- `isNaN()`会强制将参数转换成数字
- `Number.isNaN`不会强制将参数转换成数字，只有在参数是真正的数字类型，且值为 `NaN` 的时候才会返回 `true`。

- - - 
### Examples
    
    isNaN("")         //false
    Number.isNaN("")  //false
    
    isNaN("dd")         //true
    Number.isNaN("dd")  //false
    
    isNaN(null)         //false
    Number.isNaN(null)  //false
    
    isNaN(0)            //true
    Number.isNaN(0)     //false
    
    isNaN(undefined)         //true
    Number.isNaN(undefined)  //false
    
