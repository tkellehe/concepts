# Naut

A programming language designed around mathematical sequences. The language is imperative language with some extra spices.
_Naut_ also has its own __8bit__ encoding creating its own code page.

Some concepts:

    abc+=   // Sum the inputs a, b, and c then assign that to d.
    abc+    // Logically means sum the given variables that are set to the inputs of that program.
        =   // Assign a given result to a variable, since none is specified it will assign
            // that to the next undefined variable if all are used it will write over the first.
            
Has the set of characters `abcdefghijklmn` (14 chars) as variables that can be used.

```
ƙɱ:1]a // Get the ith fib.
ƙ      // Get A[ı-2]
 ɱ     // Get A[ı-1] (implicit add)
  :1]  // Everything to the left is used to generate list starting with 1.
     a // Access the list based on user provided value.
```

## Expressions

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
