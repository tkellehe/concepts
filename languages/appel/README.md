# Appel

A stack-based "golfing" esoteric language that is for fun.

## Characters

_Appel_ has its own encoding.
```
ð¬¶¤!"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~ẠḄḌẸḤỊḲḶṂṆỌṚṢṬỤṾẈỴẒạḅḍẹḥịḳḷṃṇọṛṣṭụṿẉỵẓȦḂĊḊĖḞĠḢİĿṀṄȮṖṘṠṪẆẊẎŻȧḃċḋėḟġḣŀṁṅȯṗṙṡṫẇẋẏżƁƇƊƑƓƘƝƤƬƲȤɓƈɗƒɠƙɲƥƭʋȥɦɱʠɼʂÆÇÑØŒÞæçñøœþßÐıȷ°¹²³⁴⁵⁶⁷⁸⁹¦©®«»‘’“”€¢£¥µ…¬¡¿×÷⁺⁻⁼⁽⁾ \n
```

__printables__

```
ð¬¶¤!"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~
```

 * `ð` : 
 * `¬` : 
 * `¶` : New line character.
 * `¤` : Space character.

## Memory Model
The memory model for _Appel_ is a crosshair which is essentially a vertical tape and a horizontal tap (or just two tapes...).
This can be simplified even further to consider it as one working stack and three others. These stacks we will call the
north, south, east, and west. Moving in a particular direction is to pop from one stack to the other. Now, these stacks can
be in the positions up, down, left, and right. The left and right stacks are the working stacks. The north and south stacks
represent what is to be displayed to the screen. The left stack is where all inputs are coming in and the top right stack is
the center of the working zone. Whatever is in the up stack is what is printed while the down stack is used to assist
with working on it.

## Commands


## Types

## Jumps

_Jump tokens_ are tokens that come in sets where each is connected to another.
