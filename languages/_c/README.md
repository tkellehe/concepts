# _c

_\_c_ is code-golfing language for golfing in _C++_.

## Encoding

_\_c_ uses its very own encoding where each character maps to a particular value.

|         | \_0  | \_1  | \_2  | \_3  | \_4  | \_5  | \_6  | \_7  | \_8  | \_9  | \_a  | \_b  | \_c  | \_d  | \_e  | \_f  |
|:-------:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
  **0\_** | `⁰` | `¹` | `²` | `³` | `⁴` | `⁵` | `⁶` | `⁷` | `⁸` | `⁹` | `¶` | `×` | `÷` | `⁺` | `⁻` | `⁼` |
  **1\_** | `≠` | `≤` | `≥` | `≡` | `≈` | `⁽` | `⁾` | `∞` | `¿` | `¡` | `‼` | `…` | `€` | `¢` | `£` | `¥` |
  **2\_** | `¤` | `!` | `"` | `#` | `$` | `%` | `&` | `'` | `(` | `)` | `*` | `+` | `,` | `-` | `.` | `/` |
  **3\_** | `0` | `1` | `2` | `3` | `4` | `5` | `6` | `7` | `8` | `9` | `:` | `;` | `<` | `=` | `>` | `?` |
  **4\_** | `@` | `A` | `B` | `C` | `D` | `E` | `F` | `G` | `H` | `I` | `J` | `K` | `L` | `M` | `N` | `O` |
  **5\_** | `P` | `Q` | `R` | `S` | `T` | `U` | `V` | `W` | `X` | `Y` | `Z` | `[` | `\` | `]` | `^` | `_` |
  **6\_** |<code>`</code>| `a` | `b` | `c` | `d` | `e` | `f` | `g` | `h` | `i` | `j` | `k` | `l` | `m` | `n` | `o` |
  **7\_** | `p` | `q` | `r` | `s` | `t` | `u` | `v` | `w` | `x` | `y` | `z` | `{` | <code>\|</code> | `}` | `~` | `Ạ` |
  **8\_** | `Ḅ` | `Ḍ` | `Ẹ` | `Ḥ` | `Ị` | `Ḳ` | `Ḷ` | `Ṃ` | `Ṇ` | `Ọ` | `Ṛ` | `Ṣ` | `Ṭ` | `Ụ` | `Ṿ` | `Ẉ` |
  **9\_** | `Ỵ` | `Ẓ` | `ạ` | `ḅ` | `ḍ` | `ẹ` | `ḥ` | `ị` | `ḳ` | `ḷ` | `ṃ` | `ṇ` | `ọ` | `ṛ` | `ṣ` | `ṭ` |
  **a\_** | `ụ` | `ṿ` | `ẉ` | `ỵ` | `ẓ` | `Ȧ` | `Ḃ` | `Ċ` | `Ḋ` | `Ė` | `Ḟ` | `Ġ` | `Ḣ` | `İ` | `Ŀ` | `Ṁ` |
  **b\_** | `Ṅ` | `Ȯ` | `Ṗ` | `Ṙ` | `Ṡ` | `Ṫ` | `Ẇ` | `Ẋ` | `Ẏ` | `Ż` | `ȧ` | `ḃ` | `ċ` | `ḋ` | `ė` | `ḟ` |
  **c\_** | `ġ` | `ḣ` | `ŀ` | `ṁ` | `ṅ` | `ȯ` | `ṗ` | `ṙ` | `ṡ` | `ṫ` | `ẇ` | `ẋ` | `ẏ` | `ż` | `Ɓ` | `Ƈ` |
  **d\_** | `Ɗ` | `Ƒ` | `Ɠ` | `Ƙ` | `Ɲ` | `Ƥ` | `Ƭ` | `Ʋ` | `Ȥ` | `ɓ` | `ƈ` | `ɗ` | `ƒ` | `ɠ` | `ƙ` | `ɲ` |
  **e\_** | `ƥ` | `ƭ` | `ʋ` | `ȥ` | `«` | `»` | `‘` | `’` | `“` | `”` | `ɦ` | `ɱ` | `ʠ` | `ɼ` | `ʂ` | `¦` |
  **f\_** | `©` | `®` | `Æ` | `Ç` | `Ñ` | `Ø` | `Þ` | `æ` | `ç` | `ñ` | `ø` | `þ` | `ı` | `ȷ` | <code> </code> | \n |


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
is selected based off of the next available variable name. Since nothing is done with the value, _\_c_ will infer that
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
