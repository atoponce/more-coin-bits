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

### Extracting 2-bits
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

#### Visual Construction
When looking at where the coin's center lands on the grid, if it lands in the
white area in the following image, the edges of the coin will not cross a grid
line. However, if the center of the coin lands anywhere within the red area,
then it will.

![2-bit coin flip](https://user-images.githubusercontent.com/699572/43870379-78b8c46e-9b34-11e8-9187-cab997e07733.png)

Of course, as a sanity check, the area of the red should equal the area of the
white. However, we have already proved that above.

### Extracting 3 bits
It is possible to extract 3 bits from a coin flip by applying the above
procedure into two dimensions. Rather than testing whether or not the coin
crosses any grid line, we identify if the coin:

1. Does not cross a grid line.
2. Crosses only any x-axis grid line.
3. Crosses only any y-axis grid line.
4. CRosses both the x/y axes (lands in a corner).

Using the quadratic formula that we applied above to the 1-dimensional case
(whether or not the coin crossed a grid line), can be applied on the 2-dimensional
case. The equation then becomes:

    1/4 = (l-d)^2/l^2

Solving for `l` yields:

    l = 2*d, l = 2/3*d

The solution `l = 2*d` is what we're interested in. This project provides both the
2-bits per flip and 3-bits per flip grids.

#### Visual Construction
When looking again at the coin's center, and where it lands in the grid, if it
lands in the white area in the following image, the edges of the coin will not
cross a grid line. However, if the center lands anywhere in a blue area, then it
will only cross a y-axis grid line. If the center lands anywhere in a green
area, then it will only cross an x-axis grid line. Of course, if the center of
the coin lands anywhere in a red area, then the coin will cross both the x and y
axes by landing in a corner.

![3-bit coin flip](https://user-images.githubusercontent.com/699572/43870380-7933c178-9b34-11e8-8758-f214c5f1f4af.png)

As a sanity check, the area of the white equals the area of the green which also
equals the area of the blue as well as the area of the red.

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
