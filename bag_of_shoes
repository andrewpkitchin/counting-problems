Shoe Factory Problem

There are six shoes in a bag.
There are two size 4s, two size 5s, and two size 6s.
We draw the shoes at random, without replacement.
Once two shoes are drawn, they make a pair.
An acceptable pair is one in which the size differs by a maximum of 1. So, the pair [6 4] is not acceptable.

What is the probability of drawing three acceptable pairs in a row?

Solution

First, let's reframe the problem slightly.

We can calculate the number of ways to arrange the shoes in a line where each two shoes forms a pair.

For example, one possible configuration is:

[4 4], [5 5], [6 6].

We can use the normal formula to calculate permutations with duplicate items to find the total way of ordering. We get

6!/2!2!2! = 90.

We can intuitively picture this as just removing the symmetric cases. For example, we double-count all the configurations where the 4s are permuted with one another; hence we divide by 2.

We can now approach the problem by calculating the number of configurations with unacceptable pairs. 

We will go through the calculation step by step:

Pick one of the pairs to be the first unacceptable pair - (X3)
There are two unique choices for the first item - (X2)
One unique choice for the second item - (X1)
The remaining slots should be filled by numbers from the set {4,5,5,6}. The total ways to arrange this, taking into account that we have two 5s, is 4!/2! - (X12)

In total, we have 3X2X12 = 72

We have double-counted the cases where there are exactly two unacceptable pairs. We’ll need to calculate how many there are and remove them:

Pick one of the pairs to be acceptable [5 5] - (X3)
The remaining slots should be filled by numbers from the set {4,4,6,6}. The total ways to arrange this, taking into account that we have duplicate 4s and 6s is 4!/2!2!=6. We also need to remove the two orders, which are successes, namely [4 4] [6 6] and [6 6] [4 4]. So, we get 6-2 = 4 - (X4)

In total, we have 3X4 = 12.

Putting our two calculations together gives us 72 - 12 = 60 ways of arranging the items so that they contain at least one unacceptable pair.

Since we know the total unique configurations and the number of unacceptable, we can now see that the number of acceptable configurations is:

90-60 = 30

Given that every configuration is equally likely, the probability all three pairs being acceptable is 1/3.
