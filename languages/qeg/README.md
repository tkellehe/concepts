# Quantum Esoteric Golfing (QEG) Language

## Quantum Approximate Tensor Software (QATS)

Approximating tensor product sums and multiplications is a library (QATS) I have been working on privately.
The main reason why this library has a chance of working is with this concept.
The software takes advantage of maximizing the most probable tensor product which means it may not have the exact probability for the answer, but testing has shown that the answer is produced (especially as the number of tensor product terms are increased).
This means the language potentially can have very large number of qubits.

## Qubits

The number of qubits will grow to whatever index is attempted to be accessed.
The default value for a quint is always the zero state.

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
(Inputs may need to be separate call such that can place into variables in the correct order)

Variables can be explicitly acted on, or implicitly.
Implicit actions either involve the next unused variable or the last used variable progressing alphabetically.

Inputs into the program are automatically assigned to available variables which means it can offset the implicit variables.

### List

Lists are important when generating indexes for qubits to complete circuits on.
Therein, BigInt is very common to be the type contained in the list.

### BigInt

Can be an integer that grows the number of bits to properly represent the value.

### FixedPoint

Will grow to the appropriate number of bits for the integer part, but will require specifying the number of _"decimal"_ places.

### ComplexNumber



### Bit

A single one or zero and can be compressed to another type or other types decompressed to it.

### SuperPositionBit

A single one, zero, or `*` which means either a one or zero.
It can be converted to a bit before converting to another type.
There are different algorithms for converting it.
This ranges from either assuming all zeros, randomly picking, or even selecting based off of some criteria.

## Naming Conventions

QC bytes used in CC lines will have the dot on top.
CC bytes used in CC lines will have the dot on the bottom.

If a command is present and has a dot at the bottom, the line is assumed to be CC.
All other commands can have multiple meanings.

## Tutorials and Examples

### Hadamard

The first line is always interpreted as a CC line.
We can invoke the Hadamard gate on the default generated qubit assignments.
The `Ḣ` takes a list of qubit indexes and applied the Hadamard gate to them.
Since a variable is not provided, it assumes the last used variable.
However, that variable has not been assigned.
Therein, it will automatically generate a list of 64 qubit indexes starting at zero.
This is then assigned to the variable `a`.

Since the the qubits we're not allocated yet, they are started in the zero state.
Then we apply the Hadamard gate putting the qubits in a superposition.
The `Ṃ` measures the qubits using the QATS concept generating a Bit list into `b`, the next available variable.
The program then default prints what was assigned to the last variable if nothing was printed.
Therein, it will print random ones and zeros because all states are equally likely based on QATS best guess.

```
ḢṂ
```

This program only applies it to 64 qubits explicitly.

```
a°ḢabṂṢb
```

```
a°       # assign "a" to be [0,...,63]
  Ḣa     # pass "a" to the Hadamard gate
    bṂ   # assign "b" to be list of random 64 bits
      Ṣb # show "b" to the screen
```

### Control-Not

The simplest control gate is the control-not gate.
It takes two lists, where it applies the target
If the variable for the target has not been assigned, then it will automatically be assigned to the next size.
If the variable for the control has not been assigned, then it will generate a list of 64 indexes.
The first parameter is the control and the second is the target.

```
ĊṂ
```

Explicit version.

```
a°b1aĊabcṂṢc
```

```
a°           # assign "a" to be [0,...,63]
  b1a        # assign "b" to be "a" offset by the max of "a" +1 [64,...,127]
     Ċab     # assign all bits to be CX where "a" is control and "b" is target
        cṂ   # assign "c" to be list of 128 bits
          Ṣc # show "c" to screen
```

Here is the 16-bit version.

```
²ĊṂ
```

```
a²b1aĊabcṂṢc
```

```
a²           # assign "a" to be [0,...,15]
  b1a        # assign "b" to be "a" offset by the max of "a" +1 [16,...,31]
     Ċab     # assign all bits to be CX where "a" is control and "b" is target
        cṂ   # assign "c" to be list of 32 bits
          Ṣc # show "c" to screen
```

## Commands

### Quick List Assignments

|  Symbol  | Description | Syntax |
|:--------:|:------------|:------:|
| `°` | Assign the next available variable to the list `[0,...,63]`. | __{var}__`°` |
| `¹` | Assign the next available variable to the list `[0,...,31]`. | __{var}__`¹` |
| `²` | Assign the next available variable to the list `[0,...,15]`. | __{var}__`²` |


## Encoding

|         | \_0  | \_1  | \_2  | \_3  | \_4  | \_5  | \_6  | \_7  | \_8  | \_9  | \_a  | \_b  | \_c  | \_d  | \_e  | \_f  |
|:-------:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
  **0\_** | `°` | `¹` | `²` | `³` | `⁴` | `⁵` | `⁶` | `⁷` | `⁸` | `⁹` | `¶` | `×` | `÷` | `⁺` | `⁻` | `⁼` |
  **1\_** | `≠` | `≤` | `≥` | `≡` | `≈` | `⁽` | `⁾` | `∞` | `¿` | `¡` | `‼` | `…` | `€` | `¢` | `£` | `¥` |
  **2\_** |<code> </code>| `!` | `"` | `#` | `$` | `%` | `&` | `'` | `(` | `)` | `*` | `+` | `,` | `-` | `.` | `/` |
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
  **f\_** | `©` | `®` | `Æ` | `Ç` | `Ñ` | `Ø` | `Þ` | `æ` | `ç` | `ñ` | `ø` | `þ` | `ı` | `ȷ` | `¤` | `½` |

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
