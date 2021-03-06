These problems were generated as described in 'A Study of Symmetry Breaking Predicates and Model Counting' by Wenxi Wang, Muhammad Usman, Alyas Almaawi, Kaiyuan Wang, Kuldeep S. Meel and Sarfraz Khurshid:

Use the Alloy tool (https://alloytools.org/) with the following input program

```
module nqueens -- name of the specification
sig Queen {} -- set of queen atoms
one sig Board { state: Queen -> Int -> Int } -- one board
fact StateOkay {
all q: Queen | one q.(Board.state) -- each queen occupies exactly one cell
all x: Queen.(Board.state).Int | ValidIndex[x] -- all x-coordinates are valid
all y: Int.(Queen.(Board.state)) | ValidIndex[y] -- all y-coordinates are valid
all disj q, r: Queen | q.(Board.state) != r.(Board.state) } -- queens do not share cells
pred ValidIndex[x: Int] { x.gte[0] and x.lte[(#Queen).minus[1]] } -- x >= 0 && x <= |Queen|-1
fun X[q: Queen]: Int { (q.(Board.state)).Int } -- x-coordinate of q
fun Y[q: Queen]: Int { Int.(q.(Board.state)) } -- y-coordinate of q
fun Abs[x: Int]: Int { x.lt[0] implies negate[x] else x } -- absolute value of x
pred SameRow[q, r: Queen] { X[q] = X[r] } -- q and r are in the same row
pred SameColumn[q, r: Queen] { Y[q] = Y[r] } -- q and r are in the same column
pred SameDiagonal[q, r: Queen] { -- q and r share a diagonal
Abs[X[q].minus[X[r]]] = Abs[Y[q].minus[Y[r]]] }
pred NQueensProblem { -- no queen attacks another queen
all disj q, r: Queen | !SameRow[q, r] and !SameColumn[q, r] and !SameDiagonal[q, r] }
run NQueensProblem for 5 int, exactly 8 Queen
```

Changing the last line to control the n (in nqueens) and the amount of bits to use to represent integers. E.g. 5 bits are sufficient for n=8 as 1 bit for the sign and 4 to represent [0-15].







