# Modular-Arithmetic
A cheat sheet of modular arithmetic formulas, with extension to the real numbers

![clock2](media/clock2.png "A clock is frequently used to demonstrate the concept of modular arithmetic")

# Relation to floor/ceil
These formulas can be useful for understandoing how the modulo operator behaves with negative and complex operands
- $`a \bmod m = a - m \lfloor a/m \rfloor`$
- $`a \bmod m = a + m \lceil -a/m \rceil`$
- $`\lfloor a \rfloor = -\lceil -a \rceil`$
- $`\lceil a \rceil = -\lfloor -a \rfloor`$

Reference:
- Todo

# Modulus conversion
For real numbers:
- $`a \bmod m = (a x \bmod{m x}) / x`$
- $`a \bmod m = x (a / x \bmod{m / x})`$

Proof:
- $`a \bmod m = a - m \lfloor a/m \rfloor`$
- $`(a x \bmod{m x}) / x = (a x - m x \lfloor a x/(m x) \rfloor) / x`$
- $`(a x - m x \lfloor a x/(m x) \rfloor) / x = a - m \lfloor a/m \rfloor`$
- (all $`x`$'s cancel out)

# Addition
For real numbers:
- $`(a + b) \bmod m = (a \bmod m + b \bmod m) \bmod m`$

Reference:
- Todo

# Multiplication
For integers:
- $`a b \bmod m = (a \bmod m) (b \bmod m) \bmod m`$

Reference:
- Todo

For real $`a`$ and integer $`b`$ and $`m`$:
- $`a b \bmod m = (a \bmod m) b \bmod m`$

Proof:
- Let $`n`$ be an integer
- If $`a b \bmod m = (a \bmod m) b \bmod m`$, then we can add a multiple of $`m`$ ($`n m`$) to $`a`$ without changing the result, since:
  - $`a + n m \bmod m = (a \bmod m) + (n m \bmod m) \bmod m`$
  - $`(n m \bmod m) = 0`$
  - $`a + n m \bmod m = a \bmod m`$
- $`a b \bmod m = (a \bmod m) b \bmod m = (a + n m) b \bmod m = (a + n m \bmod m) b \bmod m`$
- $`(a + n m) b \bmod m = a b + n m b \bmod m`$
- $`n m b \bmod m = 0`$
- $`a b + n m b \bmod m = a b \bmod m`$

