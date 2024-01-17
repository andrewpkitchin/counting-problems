**Tic Tac Toe** - The possible states on a 3x3 board

**Bounded Above** - The number of possible states is bounded above by 9! Why? There are 9 possibilities for the first choice, 8 for the second, etc.
9! = 362880

By no means is this a sharp bound since this number counts states that are impossible in a real game. For example, the boards which contain two winning lines for X are counted.

**How to do better?** - We will document a formula to give intuition on how we might enumerate all of the different legal game states. Some of the terms in the calculation are unnecessary and are only included to aid with consistency and explanation.

Recall - If we want to count the ways to choose k things from n things we use the binomial coefficient formula n CHOOSE k = n!/ k!(n-k)!. Remember we are dividing by k! to account for the reorderings we are counting when we use n P k = n!/(n-k)!. 

Essentially the way to build the formula for each set of states uses the following logic:

There are nine squares on the board. If we always consider placing n X’s first (where 0<n<6) the first bracketed term in each of our expressions will be of the form (9 CHOOSE n).

The second bracketed term will capture the number of O’s we are placing and will be of the form: (9-n CHOOSE k) where k is the number of O’s being placed.
Finally, once we have placed enough X’s or O’s for victories to happen, we subtract a term to account for this.

**Zero X’s and zero O’s** - (9 CHOOSE 0) * (8 CHOOSE 0) = 1

**One X and zero O’s** - (9 CHOOSE 1) * (8 CHOOSE 0) = 9

**One X’s and one O** - (9 CHOOSE 1) * (8 CHOOSE 1) = 72

**Two X’s and one O** - (9 CHOOSE 2) * (7 CHOOSE 1) = 252

**Two X’s and two O’s** - (9 CHOOSE 2) * (7 CHOOSE 2) = 756

**Three X’s and two O’s** - (9 CHOOSE 3) * (6 CHOOSE 2) = 1260

**Three X’s and three O’s** - (9 CHOOSE 3) * (6 CHOOSE 3) - 8 * (6 CHOOSE 3) = 1520

We have subtracted 8 * (6 CHOOSE 3) to account for all of the board states (with three X’s and three O’s) that contain a win for X. There are 8 win lines and (6 CHOOSE 3) ways to place the O’s. NOTE: Thinking about calculating the number of states, we don’t need to consider the order in which the three X’s, or three O’s, are placed.     

**Four X’s and three O’s** - (9 CHOOSE 4) * (5 CHOOSE 3) - 8 * (6 CHOOSE 4) = 1140

We have subtracted 8 * (6 CHOOSE 4) to account for all of the board states (with four X’s and three O’s) that contain a win for O. There are 8 win lines and (6 CHOOSE 4) ways to place the X’s.  

**Four X’s and four O’s** - (9 CHOOSE 4) * (5 CHOOSE 4) - 8 * (6 CHOOSE 4) * 2 = 390

We have subtracted 8 * (6 CHOOSE 4) * 2 to account for all of the board states (with four X’s and four O’s) that contain a win for X. Here, we will think in terms of placing three X’s, then four O’s, then the final X. Hence, 8 for the win lines, (6 CHOOSE 4) ways to place the four O’s, and two ways to place the last X.  

**Five X’s and four O’s** - (9 CHOOSE 5) * (4 CHOOSE 4) - 8 * (6 CHOOSE 5) = 78

We have subtracted 8 * (6 CHOOSE 5) to account for all of the board states (with five X’s and four O’s) that contain a win for O. There are 8 win lines and (6 CHOOSE 5) ways to place the X’s.  

**Result -** Summing all of these states gives **5,478** possible legal states for the game. Elsewhere, you may see the figure stated as 5,477, which discounts the empty board.

**A Note on Symmetry** - We have not considered that fundamentally, many states are equivalent up to symmetry. For example, the 9 choices for placing one X and zero O’s can be derived by applying rotations to three states - an X in a corner, an X in the middle spot, and an X in a middle edge spot. Therefore instead of 9 states, we would only count 3.

