### Variables and Mutability

- by default variables are immutable

```
// immutable
let x = 5; // can not change the value x = 6
//mutable
let mut x = 6; // can change the value x = 5
```

### Contants

- contants variables must always annotate the type
```
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```

### Shadowing

```
let x = 5;
{
    let x = x + 2;
    println!("line 1: x = {x}");
}
println!("line 2: x = {x}");
```

### Data types


- Scalar type:
```
Length	Signed	Unsigned
8-bit	i8	    u8
16-bit	i16	    u16
32-bit	i32	    u32
64-bit	i64	    u64
128-bit	i128	u128
arch	isize	usize
```

```
Number literals	Example
Decimal	        98_222
Hex	            0xff
Octal	        0o77
Binary	        0b1111_0000
Byte (u8 only)	b'A'
```

- Floating-Point Types
```
fn main() {
    let x = 2.0; // f64

    let y: f32 = 3.0; // f32
}
```
- Numeric Operations
```
fn main() {
    // addition
    let sum = 5 + 10;

    // subtraction
    let difference = 95.5 - 4.3;

    // multiplication
    let product = 4 * 30;

    // division
    let quotient = 56.7 / 32.2;
    let floored = 2 / 3; // Results in 0

    // remainder
    let remainder = 43 % 5;
}
```
- The Boolean Type
```
fn main() {
    let t = true;

    let f: bool = false; // with explicit type annotation
}
```
- The Character Type
```
fn main() {
    let c = 'z';
    let z: char = 'ℤ'; // with explicit type annotation
    let heart_eyed_cat = '😻';
}
```

- Compound Types

```
fn main() {
    let tup: (i32, f64, u8) = (500, 6.4, 1);

    let tup = (500, 6.4, 1);

    let (x, y, z) = tup;

    let x: (i32, f64, u8) = (500, 6.4, 1);

    let five_hundred = x.0;

    let six_point_four = x.1;

    let one = x.2;

    let a = [1, 2, 3, 4, 5];

    let months = ["January", "February", "March", "April", "May", "June", "July",
              "August", "September", "October", "November", "December"];

    let a: [i32; 5] = [1, 2, 3, 4, 5];

    let first = a[0];
    let second = a[1];
}
```

### Functions

```
fn main() {
    println!("Hello, world!");
    another_function();
    print_labeled_measurement(5, 'h');
}

fn another_function() {
    println!("Another function.");
}

fn print_labeled_measurement(value: i32, unit_label: char) {
    println!("The measurement is: {value}{unit_label}");
}
```

### Statements and Expressions
```
fn main() {
    let y = {
        let x = 3;
        x + 1
    };

    println!("The value of y is: {y}");
}
```


### Functions with Return value

```
fn five() -> i32 {
    5 //do not have ";" at the end: expression without ; and statement with ;
}

fn main() {
    let x = five();

    println!("The value of x is: {x}");
}
```

### Control Flow

- if Expression

```
fn main() {
    let number = 3;

    if number < 5 {
        println!("condition was true");
    } else {
        println!("condition was false");
    }
}
```

```
fn main() {
    let number = 3;

    if number != 0 { //Rust do not automatically try to convert non-Booleans types as a Boolean
        println!("number was something other than zero");
    }
}
```

```
fn main() {
    let number = 6;

    if number % 4 == 0 {
        println!("number is divisible by 4");
    } else if number % 3 == 0 {
        println!("number is divisible by 3");
    } else if number % 2 == 0 {
        println!("number is divisible by 2");
    } else {
        println!("number is not divisible by 4, 3, or 2");
    }
}
```

```
fn main() {
    let condition = true;
    let number = if condition { 5 } else { 6 };

    println!("The value of number is: {number}");
}
```

### Repetition with Loops

- Repeating Code with `loop`

```
fn main() {
    let mut counter = 0;

    let result = loop {
        counter += 1;

        if counter == 10 {
            break counter * 2;
        }
    };

    println!("The result is {result}");
}
```

- Loop Labels to Disambiguate Between Multiple Loops

```
fn main() {
    let mut count = 0;
    'counting_up: loop {
        println!("count = {count}");
        let mut remaining = 10;

        loop {
            println!("remaining = {remaining}");
            if remaining == 9 {
                break;
            }
            if count == 2 {
                break 'counting_up;
            }
            remaining -= 1;
        }

        count += 1;
    }
    println!("End count = {count}");
}
```
