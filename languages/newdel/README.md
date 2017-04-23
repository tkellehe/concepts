# Newdel

A language dedicated to code golfing ASCII Art and Animation. The current version of _Noodel_ does not handle string manipulation
very well. So, I am going to attempt to redefine the language with more of an actual design. Just as some notes, I would like to
incorporate the language _Charcoal_ which does a fantistic job at turtle like ASCII art, but does not handle animations very well.
_Noodel_ did well with animations, but if there was a complicated string of any sort it would fail.

## Characters

    <newline><space>!"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~¶
    ẠḄḌẸḤỊḲḶṂṆỌṚṢṬỤṾẈỴẒ
    ạḅḍẹḥịḳḷṃṇọṛṣṭụṿẉỵẓ
    ȦḂĊḊĖḞĠḢİĿṀṄȮṖṘṠṪẆẊẎŻ
    ȧḃċḋėḟġḣŀṁṅȯṗṙṡṫẇẋẏż
    ƁƇƊƑƓƘƝƤƬƲȤ
    ɓƈɗƒɠƙɲƥƭʋȥ
    ɦɱʠɼʂ
    ÆÇÑØŒÞ
    æçñøœþ
    ßÐıȷ¦©®
    «»‘’“”
    °¹²³⁴⁵⁶⁷⁸⁹
    ¤€¢£¥µ…¬¡¿×÷⁺⁻⁼⁽⁾

## Data Types

 - __String__ : This is the only data type and only stores the _printable_ characters.
 - __Number__ : A mere interpretation of a string as a base 97 number.
 - __Array__  : An array is affectively a single variable stack.

### String Compression

## Operators

 - `⁺` : Sum all input stacks and duplicate output into each output stack.

### Variable Stacks

The set `ƁƇƊƑƓƘƝƤƬƲȤ` represents a set of stacks that can be added to as an input stack or an output stack. The upper
case is for adding as an input stack while the lower case is for adding as an output stack.

### Adding Ins and Outs

This is how operators figure out where to get inputs and where to place their outputs.

## Loops and Functions

## Painting

### Turtles

### Paths
