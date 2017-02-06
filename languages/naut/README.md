# Naut

A programming language designed around mathematical sequences. The language is imperative language with some extra spices.
_Naut_ also has its own __8bit__ encoding creating its own code page.

## Variables
            
_Naut_ has the set of characters `abcdefghijklmn` (14 chars) as variables that can be used. The input
to that particular function will automatically be assigned to the corresponding variable as long as it is less that 14.
As in, the first input will be assigned to `a`, the second input assigned to `b`, and so on. A variable can either
store a __list__ or a __value__.

```
ƙ+ɱ:1]a // Get the ith fib.
ƙ       // Get A[ı-2]
 +      // Add the left and right operands.
  ɱ     // Get A[ı-1]
   :1]  // Everything to the left is used to generate list starting with 1.
      a // Access the list based on user provided value.
```

## Lists and Values

Has two data types, __lists__ and __values__. __Values__  are numerical objects that hold a real and imaginiary portion
in which is stored as two fixed point values. __Lists__ are object that contain elements that are either
__lists__ or __values__. Also, the __values__ are stored in the form of a base 2<sup>16</sup> number in order to be
nicely converted to _UTF-8_ strings for displaying also allow for storing high precision values with a fixed error.

## Expressions

An expression is a set of tokens evaluated as a single token in which either produces a list or value.

```

```

Expressions can also have implied closing or opening parentheses.

```
a^(b+c // a to the power of b + c.
a      // The first input into the function.
 ^     // Take left hand token to the power of the right hand token.
  (b+c // Treated as a single token.
  (    // Collects all tokens to the right.
   b   // The second input into the function.
    +  // Add left and and right tokens.
     c // The third input into the function.
```

```
a-b)*c // Multiply c by the difference of a and b.

a-b)   // Calculate the difference.
a      // Get the value of a.
 -     // Subctract b from a.
  b    // Get the value of b.
   )   // Capture the tokens and evaluate as a single expresion.
   
    *  // Multiply left and right expressions.
     c // Get the value of c.
```

## Functions

Every line repesents a given function that can be accessed from other functions relatively where
the first function executed is the top most. A given function can only access seven in either direction.
These are repesented by the character set `ABCDEFGHIJKLMN`.

```
( // The first function and entry point into the script.
( // <- H | +1
( // <- I | +2
( // <- J | +3
( // <- K | +4
( // <- L | +5
( // <- M | +6
( // <- N v +7
( // <- A ^ -7
( // <- B | -6
( // <- C | -5
( // <- D | -4
( // <- E | -3
( // <- F | -2
( // <- G | -1
```

## Encoding

```
ð¬¶¤ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz.!?,0123456789:;"'_<=>*+-/\@#$%&^|()[]{}`~
ẠḄḌẸḤỊḲḶṂṆỌṚṢṬỤṾẈỴẒȦḂĊḊĖḞĠḢİĿṀṄȮṖṘṠṪẆẊẎŻạḅḍẹḥịḳḷṃṇọṛṣṭụṿẉỵẓȧḃċḋėḟġḣŀṁṅȯṗṙṡṫẇẋẏżƁƇƊƑƓƘƝƤƬƲȤɓƈɗƒɠɦƙɱ
ɲƥʠɼʂƭʋȥÆÇÐÑØŒÞßæçıȷñøœþ€¢£¥…µ¡¿×÷¦©®«»‘’“”°¹²³⁴⁵⁶⁷⁸⁹⁺⁻⁼⁽⁾
```
