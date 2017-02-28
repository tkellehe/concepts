#Pikel

A tape based esoteric language and that is about all I can think of to explain it.

#Operations

 - ` ` : NOP.
 - `>` : Move one cell to the right creating if one does not exist.
 - `<` : Move one cell to the left creating if one does not exist.
 - `+` : Add cell on the right to the current cell.
 - `-` : Subtract cell on the right from the current cell.
 - `*` : Multiply cell on the right with the current cell.
 - `/` : Divide cell on the right with the current cell.
 - `.` : Append contents of the cell on the right to the current cell.
 - `,` : Prepend contents of the cell on the right to the current cell.
 - `|` : Split current cell in half forcing larger portion right.
 - `@` : Flip the tape based off of the current cell.
 - `^` : Push current cell to the output stream.
 - `?` : End execution if cell is zero.
 - `!` : End execution if cell is not zero.
 - `f` : Copy content of current cell and end execution after that amount (if multiple item uses length).
 - `F` : Consume current cell and end execution after that amount (if multiple item uses length).
 - `=` : If cell to the right equals current cell, then spawn new cell with a one.
 - `~` : If cell is truthy, make falsey. If cell is falsey, make truthy. (negate)
 - `0` : Push zero then jump left.
 - `1` : Push
 
#Esoteric Part

Each line represents an independent line of execution looping endlessly each tick. The script does not end until all lines have completed execution.
