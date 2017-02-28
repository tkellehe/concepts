#Pikel

A tape based esoteric language and that is about all I can think of to explain it.

#Operations

 - <code> </code> : NOP.
 - `>` : Move one cell to the right creating if one does not exist.
 - `<` : Move one cell to the left creating if one does not exist.
 - `j` : Jump number of cells to the right based off of the current cell.
 - `J` : Jump number of cells to the left based off of the current cell.
 
 - `+` : Add cell on the right to the current cell.
 - `-` : Subtract cell on the right from the current cell.
 - `*` : Multiply cell on the right with the current cell.
 - `/` : Divide cell on the right with the current cell.
 - `=` : If cell to the right equals current cell, then spawn new cell with a one.
 - `~` : If cell is truthy, make falsey. If cell is falsey, make truthy. (negate)
 
 - `.` : Append contents of the cell on the right to the current cell.
 - `,` : Prepend contents of the cell on the right to the current cell.
 - `:` : Pop off last item creating a new cell to the right.
 - `;` : Pop off first item creating a new cell to the left.
 - `|` : Split current cell in half forcing larger portion right.
 - `@` : Flip the tape based off of the current cell.
 - `s` : Swap left cell with right cell and right cell with left cell.
 - `S` : Move cell on the left to the right.
 - `r` : Remove current cell.
 
 - `^` : Push current cell to the output stream.
 - `\` : Push cell to the right to output stream.
 - `c` : Clear the screen.
 - `C` : Clear the screen and push current cell to the output stream.
 
 - `d` : Delay current line by the number of milliseconds in the current cell.
   - `s` : Delay current line for a second.
   - `h` : Delay current line for a half a second.
   - `q` : Delay current line for a quarter of a second.
   - `e` : Delay current line for an eighth of a second.
 - `D` : Delay current line by the number of milliseconds in the cell to the right. 
 
 - ``` : Run line exactly once.
 - `?` : End execution if cell is zero.
 - `!` : End execution if cell is not zero.
 - `f` : Copy content of current cell and end execution after that amount (if multiple item uses length).
 - `F` : Consume current cell and end execution after that amount (if multiple item uses length).
 
 - `0` : Set current cell to zero.
 - `1` : Increment current cell by one.
 - `2` : Increment current cell by two.
 - `3` : Increment current cell by three.
 - `4` : Increment current cell by four.
 - `5` : Increment current cell by five.
 - `6` : Increment current cell by six.
 - `7` : Increment current cell by seven.
 - `8` : Increment current cell by eight.
 - `9` : Increment current cell by nine.
 - `#` : Start number stream and consume until no more digits then increment current cell by the value. If no numbers then append all cells to the right and prepend all cells to the left to the current cell.
 - `_` : Start number stream and consume until no more digits then decrement current cell by the value. If no numbers then flip sign or reverse string.
 
 - `"` : Start consuming ASCII characters until an ending quote is found (support escaping `\`) then append set to current cell.
 - `'` : Start consuming `[a-zA-Z0-9]` characters until a character not in the set is found then append set to current cell.
 - `n` : Append a new line to current cell.
 - `z` : Start consuming `[0-9a-zA-Z]` and treat as a base 62 number and increment current cell.
 - `Z` : Start consuming `[0-9a-zA-Z]` and treat as a base 62 number and decrement current cell.
 
 - `]` : Access current cell as an array and based off of the cell to the left access that element wrapping if needed then insert new item to the right of the current cell and move right.
 - `[` : Access current cell as an array and based off of the cell to the right access that element wrapping if needed then insert new item to the left of the current cell and move left.
 
 
#Esoteric Part

Each line represents an independent line of execution looping endlessly each tick. The script does not end until all lines have completed execution.
