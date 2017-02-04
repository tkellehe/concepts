# Naut

A programming language designed around mathematical sequences. The language is imperative language with some extra spices.
_Naut_ also has its own __8bit__ encoding creating its own code page.

Example concept:

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

##Encoding

```
ð¬¶¤ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz.!?,0123456789:;"'_<=>*+-/\@#$%&^|()[]{}`~
ẠḄḌẸḤỊḲḶṂṆỌṚṢṬỤṾẈỴẒȦḂĊḊĖḞĠḢİĿṀṄȮṖṘṠṪẆẊẎŻạḅḍẹḥịḳḷṃṇọṛṣṭụṿẉỵẓȧḃċḋėḟġḣŀṁṅȯṗṙṡṫẇẋẏżƁƇƊƑƓƘƝƤƬƲȤɓƈɗƒɠɦƙɱ
ɲƥʠɼʂƭʋȥÆÇÐÑØŒÞßæçıȷñøœþ€¢£¥…µ¡¿×÷¦©®«»‘’“”°¹²³⁴⁵⁶⁷⁸⁹⁺⁻⁼⁽⁾
```
