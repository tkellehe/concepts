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

Like _C++_ there are basic primitive types where each type is represented as a specific token.

## Declaring Variables

```
ȥ-7
```

The `ȥ` instantiates a new `intV` type which will be assigned the value following the token. The name of the variable
is selected based off of the next available variable name. Since nothing is done with the value __c_ will infer that
it needs to print the declared variable.

```
#include <iostream>
typedef long long int intV;

int main(void)
{
  intV a = -7;
  std::cout << a << std::endl;
  return 0;
}
```
