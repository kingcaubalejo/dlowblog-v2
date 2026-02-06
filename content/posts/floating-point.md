---
author: "dlowrenz"
title: "What is Floating-Point Decimal?"
date: "2026-02-05"
description: "One of my many articles."
tags: [
    "markdown",
    "text",
]
---

## Introduction

As humans, we have made enormous progress in technology, turning from impossible to possible. From stunning graphics and real-time chat to complex computation that require calculations that are scientific.

A famous french visual artist once said.

> L’exactitude n’est pas la vérité.  
> Exactitude is not the truth.

It seems that it is also the same in computing. There a figures or numbers that appears to be a precise but hide approximations.

And this leads to an important concept in computing: **Floating-Point Decimal Precision**

Okay? What is it?

---

## What is Floating-Point Decimal Precision?

It is a number that represents real numbers (numbers with fractional parts) using a format similar to scientific-notation but in base 2 (binary) instead of base 10 (decimal)

Alright? I need more.

Floating-point numbers are stored as scientific notation in base 2.

```

Value = sign x mantissa x base^exponent

```

E.g: in decimal:

```

1.23 x 10^2 = 123

```

E.g: in binary: floating-point numbers look more like:

```

1.011 x 2^4

```

This allows computers to efficiently represent very large and very small numbers-but not all decimal values can be represented exactly in binary.

---

## Why do floating-point precision issues exist?

### The Problem: Binary Representation

Many decimal numbers that are simple for humans cannot be represented exactly in binary.

E.g:

```

0.1 (decimal) = 0.00011001100110011... (binary, repeating forever)

````

Since computers have limited memory, they must truncate or round this repeating binary value. That small rounding error is where problems begin.

---

## Common Issues with Floating-Point Decimals

### Precision and Rounding Errors

Because of rounding, calculations may produce slightly incorrect results.

E.g:

```js
0.1 + 0.2 === 0.3 // false
````

Actual result:

```
0.30000000000000004
```

Each operation introduces a tiny error, and over many calculations, those errors can accumulate.

---

### Limited Precision

Floating-point numbers have a fixed number of bits to store values. Once that limit is reached:

* Extra digits are dropped
* Accuracy decreases for very long or very small numbers
* Exact equality comparisons become unreliable

---

### Comparison Problems

Comparing floating-point numbers directly using `==` or `===` is dangerous.

Instead of:

```js
A === B
```

You should compare with a tolerance (epsilon):

```js
0.1 + 0.2 === 0.3 // false
var a = 0.5;
var b = 0.6;
var result = a + b

console.log(result)
console.log(a + b === 1.1)
console.log(Math.abs((0.1 + 0.2) - 0.3) < 1e-9)
```

---

## What Is the IEEE 754 Standard?

The IEEE 754 standard defines how floating-point numbers are stored and computed across almost all modern systems.

### Key Features of IEEE 754

* Defines single precision (32-bit) and double precision (64-bit)
* Specifies rounding rules
* Handles special values:

  * NaN (Not a Number)
  * Infinity
  * -Infinity

---

### Why It Matters

Because almost all programming languages follow IEEE 754, floating-point behavior is consistent across platforms—but the precision limitations are also universal.

---

## Practical Tips for Handling Floating-Point Precision

### 1. Avoid Floating-Point for Money

Never use floating-point numbers for financial calculations.

Instead:

* Use integers (e.g., cents instead of dollars)
* Use decimal libraries (e.g., BigDecimal, Decimal.js)

---

### 2. Use Rounding Carefully

Round values only when displaying, not during internal calculations.

Example:

```js
Number(value.toFixed(2))
```

---

### 3. Compare Using Epsilon

Always compare floating-point numbers with a tolerance.

---

## Conclusion

Floating-point is not precise by nature. With the help of the standard IEEE 754, it becomes precise.

I saw a video that explains it very well. Might as well share it here as an additional great resource.

https://www.youtube.com/watch?v=dQhj5RGtag0

{{< css.inline >}}
<style>
.canon { background: white; width: 100%; height: auto; }
</style>
{{< /css.inline >}}