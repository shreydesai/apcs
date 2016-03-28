# Base Conversion

## Binary to Decimal

Problem: Convert `101011101` to a decimal number (`base 10`). 

**Step 1:** Align the digits of a binary number with the powers of `2`.

| 1 | 0 | 1 | 0 | 1 | 1 | 1 | 0 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 2^8 | 2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0 |

**Step 2:** Calculate the powers of `2` on the bottom table.

| 1 | 0 | 1 | 0 | 1| 1 | 1 | 0 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |

**Step 3:** If there is a `1` in the table, highlight the corresponding power of `2`. If there is a `0` in the table, ignore the corresponding power of `2`.

| 1 | 0 | 1 | 0 | 1| 1 | 1 | 0 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **1** | 0 | **1** | 0 | **1** | **1** | **1** | 0 | **1** |
| **256** | 128 | **64** | 32 | **16** | **8** | **4** | 2 | **1** |

**Step 4:** Add up all the powers of `2` that are bolded on the bottom.

```
256 + 64 + 16 + 8 + 4 + 1 = 349
```

## Hexadecimal to Decimal

Reference: Before doing any hexadecimal to decimal conversions, make sure you know what different letters stand for. Here is a table for hexadecimal reference:

| 10 | 11 | 12 | 13 | 14 | 15 |
| --- | --- | --- | --- | --- | --- |
| A | B | C | D | E | F |

Problem: Convert `7DE` to a decimal number (`base 10`).

**Step 1:** Align the digits of a binary number with the powers of `16`.

| 7 | D | E |
| --- | --- | --- |
| 16^2 | 16^1 | 16^0 |

**Step 2:** Calculate the powers of `16` on the bottom table and change the alphabet letters in the top table to numerical values by referencing the hexadecimal table above.

| 7 | 13 | 14 |
| --- | --- | --- |
| 256 | 16 | 1 |

**Step 3:** Multiply the number on the top table with the number on the bottom table and add the values to find the decimal number.

```
7(256) + 13(16) + 14(1) = 2014
```

## Decimal to Binary

Problem: Convert `143` into a binary number (`base 2`).

Overall Strategy:
* Divide the number by `2`, and save the remainder (`1` or `0`) in a list
* Divide the quotient from above by `2`, and save the remainder (`1` or `0`) in a list
* Repeat above until 1) the quotient is `0` and 2) the final remainder is either `1` or `0`
* Read the list backwards, and that will be your decimal number

Example:

```
1. 143 % 2 = 1, List = [1]
2. 71 % 2 = 1, List = [1, 1]
3. 35 % 2 = 1, List = [1, 1, 1]
4. 17 % 2 = 1, List = [1, 1, 1, 1]
5. 8 % 2 = 0, List = [1, 1, 1, 1, 0]
6. 4 % 2 = 0, List = [1, 1, 1, 1, 0, 0]
7. 2 % 2 = 0, List = [1, 1, 1, 1, 0, 0, 0]
8. 1 % 2 = 1, List = [1, 1, 1, 1, 0, 0, 0, 1]
```

Once you read the list backwards, you will reach the final answer of `10001111`.

## Decimal to Hexadecimal

Problem: Convert `143` into a hexadecimal number (`base 16`).

Overall Strategy:
* Divide the number by `16`, and save the remainder (less than `16`) in a list
* Divide the quotient from above by `16`, and save the remainder (less than `16`) in a list
* Repeat above until 1) the quotient is `0` and 2) the final remainder is less than `16`
* Read the list backwards, and that will be your hexadecimal number

Example:

```
1. 143 % 16 = 15, List = [15]
2. 8 % 16 = 15, List = [15, 8]
```

Once you read the list backwards, you will reach the final answer of `8F`. In case you didn’t catch it, the `15` in the list is represented by the alphabetical character `F`, as this is the standard hexadecimal conversion.

