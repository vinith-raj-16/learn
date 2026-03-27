# 🔧 Bitwise Operators in Go

Bitwise operators perform operations on integers at the **bit level**. They are particularly useful in:

- Low-level or embedded programming
- Cryptography
- Performance optimizations
- Permission and flag checks
- Binary data manipulation

In Go, bitwise operations are supported on integer types like `int`, `int64`, `uint8`, etc.

---

## 🧠 Integer to Binary (for understanding)

```go
fmt.Printf("%b\n", 5) // Output: 101
fmt.Printf("%b\n", 3) // Output: 011

```
## AND (&)
***Sets each bit to 1 if both bits are 1.***
```go
a := 5        // 101
b := 3        // 011
fmt.Println(a & b) // Output: 1 (001)

5 = 0 1 0 1
3 = 0 0 1 1
------------
1 = 0 0 0 1
```

##  🚫 OR (|)

***Sets each bit to 1 if one or both bits are 1.***
```go

a := 5        // 101
b := 3        // 011
fmt.Println(a | b) // Output: 7 (111)

5 = 0 1 0 1
3 = 0 0 1 1
------------
7 = 0 1 1 1
```

## 🔀 XOR (^)
***Sets each bit to 1 only if the bits are different.***

```go

a := 5        // 101
b := 3        // 011
fmt.Println(a ^ b) // Output: 6 (110)

5 = 0 1 0 1
3 = 0 0 1 1
------------
6 = 0 1 1 0


```
## ❌ NOT (^ – Unary)
***Inverts all the bits.***

```go

a := 5        // 0000...0101 (depends on system architecture)
fmt.Println(^a) // Output: -6 (in two's complement form)

```

### ⏪ Left Shift (<<)
***Shifts bits to the left, filling with 0. Equivalent to multiplying by 2 for each shift.***

```go
a := 5        // 101
fmt.Println(a << 1) // Output: 10 (1010)
fmt.Println(a << 2) // Output: 20 (10100)

a << 1 ~=  a * 2 = 10
a << 2 ~=  a * 2 * 2 = 20
```


## ⏩ Right Shift (>>)
***Shifts bits to the right. Discards shifted bits.***

```go
a := 5        // 101
fmt.Println(a >> 1) // Output: 2 (010)
fmt.Println(a >> 2) // Output: 1 (001)


a << 1 ~=  a / 2 = 2
a << 2 ~=  (a / 2) / 2 = 1

```

**_OVERVIEW_**

| Operator | Name        | Example  | Result | Binary Explanation                         |
| :--------: | :-----------: | :--------: | :------: | :------------------------------------------: |
| `&`      | AND         | `5 & 3`  | `1`    | `101 & 011 = 001`                          |
| `\|`     | OR          | `5 \| 3` | `7`    | `101 \| 011 = 111`                         |
| `^`      | XOR         | `5 ^ 3`  | `6`    | `101 ^ 011 = 110`                          |
| `^`      | NOT (Unary) | `^5`     | `-6`   | `^000...0101 = ...1010` (two's complement) |
| `<<`     | Left Shift  | `5 << 1` | `10`   | `101 << 1 = 1010`                          |
| `>>`     | Right Shift | `5 >> 1` | `2`    | `101 >> 1 = 010`                           |

