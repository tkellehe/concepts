# _c

__c_ is code-golfing language for golfing in _C++_.

## Encoding

__c_ uses its very own encoding where each character maps to a particular value.

```
ð¬¶¤!"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~ẠḄḌẸḤỊḲḶṂṆỌṚṢṬỤṾẈỴẒạḅḍẹḥịḳḷṃṇọṛṣṭụṿẉỵẓȦḂĊḊĖḞĠḢİĿṀṄȮṖṘṠṪẆẊẎŻȧḃċḋėḟġḣŀṁṅȯṗṙṡṫẇẋẏżƁƇƊƑƓƘƝƤƬƲȤɓƈɗƒɠƙɲƥƭʋȥɦɱʠɼʂÆÇÑØŒÞæçñøœþßÐıȷ°¹²³⁴⁵⁶⁷⁸⁹¦©®«»‘’“”€¢£¥µ…¬¡¿×÷⁺⁻⁼⁽⁾ \n
```

## Hello, world!

```
ñHello,¤world!
```
Transpiles to...
```
#include <iostream>

int main(void)
{
  std::cout << "Hello, world!" << std::endl;
  return 0;
}
```

## Types

Like _C++_ there are basic primitive types :
 - char
 - unsigned char
 - bool
 - short
 - unsigned short
 - int
 - unsigned int
 - float

Some are missing from the list, but you get the picture. For __c_, there is fixed size types as well as some others.
