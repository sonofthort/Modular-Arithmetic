# Modular-Arithmetic
A cheat sheet of modular arithmetic formulas which I've found useful, with extension to the real numbers.

![clock2](media/clock2.png "A clock is frequently used to demonstrate the concept of modular arithmetic")

For formulas which I've found elsehwere, I provide references. For formulas which I've derived and haven't yet found existing references, I provide attempted proofs. Any feedback which can help improve this article would be greatly appreciated.

# Relation to floor/ceil
The following formulas can be useful for understanding how the modulo operator behaves with negative and complex operands, and for deriving other relations:
- $`a \bmod m = a - m \lfloor a/m \rfloor`$
- $`a \bmod m = a + m \lceil -a/m \rceil`$
- $`\lfloor a \rfloor = -\lceil -a \rceil`$
- $`\lceil a \rceil = -\lfloor -a \rfloor`$

Reference:
- Donald. E. Knuth. The Art of Computer Programming, Vol 1, Fundamental Algorithms. Addison-Wesley, 1972.
- http://norayr.am/papers/divmodnote.pdf
- https://medium.com/@krmayank/modulus-of-a-negative-number-a18decf3773e

# Modulus conversion
For real numbers:
- $`a \bmod m = (a x \bmod{m x}) / x`$
- $`a \bmod m = x (a / x \bmod{m / x})`$

Proof:
- $`a \bmod m = a - m \lfloor a/m \rfloor`$
- $`(a x \bmod{m x}) / x = (a x - m x \lfloor a x/(m x) \rfloor) / x`$
- $`(a x - m x \lfloor a x/(m x) \rfloor) / x = a - m \lfloor a/m \rfloor`$
- (all $`x`$'s cancel out)
- The division version maps directly to the multiplication version (by using a multiplier of $`1/x`$):
  - $`y = 1/x`$
  - $`x (a / x \bmod{m / x}) = (a y \bmod{m y}) / y`$

# Addition
For real numbers:
- $`(a + b) \bmod m = (a \bmod m + b \bmod m) \bmod m`$

Reference:
- https://www.reddit.com/r/learnmath/comments/18aia0m/modular_arithmetic_on_real_numbers
- https://math.stackexchange.com/questions/55297/what-are-the-rules-for-basic-algebra-when-modulo-real-numbers-are-involved

# Multiplication
For integers:
- $`a b \bmod m = (a \bmod m) (b \bmod m) \bmod m`$

Reference:
- https://www.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/modular-multiplication
- https://www.geeksforgeeks.org/modular-multiplication/

For real $`a`$ and integer $`b`$ and $`m`$:
- $`a b \bmod m = (a \bmod m) b \bmod m`$

Proof:
- Let $`n`$ be an integer
- If $`a b \bmod m = (a \bmod m) b \bmod m`$, then a multiple of $`m`$, $`n m`$, can be added to $`a`$ without changing the result, since:
  - $`(a + n m) \bmod m = (a \bmod m + n m \bmod m) \bmod m`$
  - $`n m \bmod m = 0`$
  - $`(a + n m) \bmod m = a \bmod m`$
- To prove that the following is true:
  - $`a b \bmod m = (a + n m) b \bmod m`$
- Reduce the right hand side and show that it matches the left hand side:
  - $`(a + n m) b \bmod m = (a b + n m b) \bmod m`$
  - $`(a b + n m b) \bmod m = (a b + n m b \bmod m) \bmod m`$
  - $`n m b \bmod m = 0`$
  - $`(a b + n m b) \bmod m = a b \bmod m`$
- Therefore, $`a`$ can be substituted with $`a \bmod m`$
