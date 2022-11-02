# Quantum Esoteric Golfing (QEG) Language

## Quantum Approximate Tensor Software (QATS)

Approximating tensor product sums and multiplications is a library (QATS) I have been working on privately.
The main reason why this library has a chance of working is with this concept.
The software takes advantage of maximizing the most probable tensor product which means it may not have the exact probability for the answer, but testing has shown that the answer is produced (especially as the number of tensor product terms are used).

## Qubit Count

The number of qubits will grow to whatever index is attempted to be accessed.

## Classical Code Lines and Quantum Circuit Lines

The first line in the program will be the _"main"_ of the program.
Each line is either a _Classical Code Line_ (CC line) or a _Quantum Circuit Line_ (QC line).
A _Classical Code Line_ can either call to another CC line or a QC line.
A _Quantum Circuit Line_ can only call to another QC line.

The concept is to use the CC lines to generate variables that the QC lines can use.
Then to process in CC lines the current state of the qubits as either some output or another input.
Therein, CC lines are merely a chain of variable assignments and calls to QC lines.

## Variables

Variables are only of type list.
Each variable can only hold a list of the same type.
There are only a finite set of variables.

Variables can be explicitly acted on, or implicitly.
Implicit actions either involve the next unused variable or the last used variable progressing alphabetically.

Inputs into the program are automatically assigned to available variables which means it can offset the implicit variables.

### List

Lists are important when generating indexes for qubits to complete circuits on.
Therein, BigInt is very common to be the type contained in the list.

### BigInt

### FixedPoint

### BitStream

### MultiBitStream

## Encoding

|         | \_0  | \_1  | \_2  | \_3  | \_4  | \_5  | \_6  | \_7  | \_8  | \_9  | \_a  | \_b  | \_c  | \_d  | \_e  | \_f  |
|:-------:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
  **0\_** | `°` | `¹` | `²` | `³` | `⁴` | `⁵` | `⁶` | `⁷` | `⁸` | `⁹` | `¶` | `×` | `÷` | `⁺` | `⁻` | `⁼` |
  **1\_** | `≠` | `≤` | `≥` | `≡` | `≈` | `⁽` | `⁾` | `∞` | `¿` | `¡` | `‼` | `…` | `€` | `¢` | `£` | `¥` |
  **2\_** |<code> </code> | `!` | `"` | `#` | `$` | `%` | `&` | `'` | `(` | `)` | `*` | `+` | `,` | `-` | `.` | `/` |
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
  **f\_** | `©` | `®` | `Æ` | `Ç` | `Ñ` | `Ø` | `Þ` | `æ` | `ç` | `ñ` | `ø` | `þ` | `ı` | `ȷ` | `¤` | `½ ` |

All characters together as a block:

```
°¹²³⁴⁵⁶⁷⁸⁹¶×÷⁺⁻⁼
≠≤≥≡≈⁽⁾∞¿¡‼…€¢£¥
 !"#$%&'()*+,-./
0123456789:;<=>?
@ABCDEFGHIJKLMNO
PQRSTUVWXYZ[\]^_
`abcdefghijklmno
pqrstuvwxyz{|}~Ạ
ḄḌẸḤỊḲḶṂṆỌṚṢṬỤṾẈ
ỴẒạḅḍẹḥịḳḷṃṇọṛṣṭ
ụṿẉỵẓȦḂĊḊĖḞĠḢİĿṀ
ṄȮṖṘṠṪẆẊẎŻȧḃċḋėḟ
ġḣŀṁṅȯṗṙṡṫẇẋẏżƁƇ
ƊƑƓƘƝƤƬƲȤɓƈɗƒɠƙɲ
ƥƭʋȥ«»‘’“”ɦɱʠɼʂ¦
©®ÆÇÑØÞæçñøþıȷ¤½
```

All characters as a single line:

```
°¹²³⁴⁵⁶⁷⁸⁹¶×÷⁺⁻⁼≠≤≥≡≈⁽⁾∞¿¡‼…€¢£¥ !"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~ẠḄḌẸḤỊḲḶṂṆỌṚṢṬỤṾẈỴẒạḅḍẹḥịḳḷṃṇọṛṣṭụṿẉỵẓȦḂĊḊĖḞĠḢİĿṀṄȮṖṘṠṪẆẊẎŻȧḃċḋėḟġḣŀṁṅȯṗṙṡṫẇẋẏżƁƇƊƑƓƘƝƤƬƲȤɓƈɗƒɠƙɲƥƭʋȥ«»‘’“”ɦɱʠɼʂ¦©®ÆÇÑØÞæçñøþıȷ¤½
```
