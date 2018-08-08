# more-coin-bits
Extracting 2 and 3 bits with every coin toss, with nothing more than one coin and a
sheet of paper.

## Introduction
Traditionally, only 1-bit of randomness can be extracted per coin flip- heads or
tails. This design uses paper with a carefully placed grid, based on each coin
diameter, to extract a uniformly distributed 2-bits from each coin toss.

## Theory
18th century mathematician Gearges-Louis Leclerc, Comte de Buffon played a
common game tossing a coin onto a tile floor, betting on whether the coin landed
squarely in the tile, or if the coin crossed the grout between tile squares.

He proposed calculating the probability `P` that a coin would cross the grout if
you knew the coin's diameter `d` and the length of a tile edge `l`.

The probability is:

    P = (l-d)^2/l^2

In this case, we want to know when the probability is exactly 50%. Thus:

    1/2 = (l-d)^2/l^2

If you know the coin's diameter, you can solve for the tile edge length:

    1/2 = (l-d)^/l^2
    l^2 = 2*(l-d)^2
    l^2 = 2*l^2-4*l*d+2*d^2
    0 = l^2-4*l*d+2d^2

Applying the quadratic formula as a solution to our quadratic equation, we can
solve for `l` and simplify, yielding

    l = d*(2+Sqrt(2)), l = d*(2-Sqrt((2))

We are only interested in the continuous distribution of probabilities in the
range of [0,1], as such, we only care about `l = d*(2+Sqrt(2))` as our solution
to finding the grid edge length, when we know the coin's diameter.

### Extracting 3 bits
It is possible to extract 3 bits from a coin flip in a couple of ways:

1. Recording the rotation of the coin as "facing north" versus "facing south".
2. Recording crossing vertical grid edges, horizontal grid edges, and both.

In the first proposal, it's not clear how much impact a common coin flip has on
rotational spin, and whether or not this is unpredictable enough to extract a
third bit from. A
[research paper about coin flipping bias](http://statweb.stanford.edu/~susan/papers/headswithJ.pdf)
suggests that coin precessing (spinning about the y-axis) is happening.

In the second proposal, the grid edges would have to be relaculated, shrinking
the area of the grid, such that a coin has equal probability of landing squarely
in the tile, without touching an edge, landing on a vertical edge only, landing
on a horizontal edge only, and landing on both edges in a corner.

Using the quadratic formula that we applied above to the 1-dimensional case
(whether or not the coin crossed a grid line), can be applied on the 2-dimensional
case by testing:

1. Not crossing any grid line.
2. Crossing only the x-axis grid lines.
3. Crossing only the y-axis grid lines.
4. Crossing both the x/y axes grid lines (corner).

The equation then becomes:

    1/2 = (l-d)^2/l^2

Solving for `l` yields:

    l = 2*d, l = 2/3*d

The solution `l = 2*d` is what we're interested in. This project provides both the
2-bits per flip and 3-bits per flip grids.

### Additional bits
Some other ideas could extract a 4th bit via colored grids. This approach, and
others are not currently investigated here.

## Execution
Print off the PDF appropriate for your coin, and flip a coin such that it lands
on the paper. Record both the face shown on the coin, and whether or not the
coin crossed a grid. You could record face type as heads (H) and tails (T), and
if it did not cross a grid edge (0) or if it did (1).

Suppose the following coins tosses were made:

    1st toss: heads, did not cross a grid edge
    2nd toss: heads, did cross an edge
    3rd toss: tails, did not cross a grid edge
    4th toss: heads, did not cross a grid edge
    5th toss: tails, did cross an edge
    6th toss: tails, did not cross a grid edge

Then the tosses could be recorded as:

    H0, H1, T0, H0, T1, T0

If the coin lands outside of the paper, you can only record one bit, the face
result, but not whether or not it crossed a grid edge, due to ambiguity.

## Common Coins
Below are commonly used coin diameters in centimeters, and their associated grid
lengths in centimeters. PDFs are found in this repository for printing. They are
broken down as:

    Nationl currency
    └── Paper type
        └── Coin PDF

### U.S. Coins

* Penny
  - Diameter: 1.905 cm
  - Grid length: 6.504 cm
* Nickel
  - Diameter: 2.121 cm
  - Grid length: 7.2415 cm
* Dime
  - Diameter: 1.791 cm
  - Grid length: 6.1148 cm
* Quarter
  - Diameter: 2.426 cm
  - Grid length: 8.2828 cm
* Half Dollar
  - Diameter: 3.061 cm
  - Grid length: 10.4509 cm
* Dollar (Sacagawea)
  - Diameter: 2.65 cm
  - Grid length: 9.0476 cm

### Canadian Coins

* Penny
  - Diameter: 1.905 cm
  - Grid length: 6.504 cm
* Nickel
  - Diameter: 2.12 cm
  - Grid length: 7.2381 cm
* Dime
  - Diameter: 1.803 cm
  - Grid length: 6.1558 cm
* Quarter
  - Diameter: 2.388 cm
  - Grid length: 8.1531 cm
* 50-cent
  - Diameter: 2.713 cm
  - Grid length: 9.2627 cm
* Loonie
  - Diameter: 2.65 cm
  - Grid length: 9.0476 cm
* Toonie
  - Diameter: 2.8 cm
  - Grid length: 9.5597 cm

### Euro Coins

* 1-cent
  - Diameter: 1.625 cm
  - Grid length: 5.548 cm
* 2-cent
  - Diameter: 1.875 cm
  - Grid length: 6.4016 cm
* 5-cent
  - Diameter: 2.125 cm
  - Grid length: 7.2552 cm
* 10-cent
  - Diameter: 1.975 cm
  - Grid length: 6.743 cm
* 20-cent
  - Diameter: 2.225 cm
  - Grid length: 7.5966 cm
* 50-cent
  - Diameter: 2.425 cm
  - Grid length: 8.2794 cm
* 1 euro
  - Diameter: 2.325 cm
  - Grid length: 7.938 cm
* 2 euro
  - Diameter: 2.575 cm
  - Grid length: 8.7915 cm
