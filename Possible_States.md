**Tic Tac Toe - Possible States on a 3x3 board**

**Bounded Above -** The number of possible states is bounded above by 9! Why? There are 9 possibilities for the first choice, 8 for the second, and so on. 

9! = 362880

This by no means is a sharp bound, since this number counts games that are impossible. For example, the boards which follow from a position where the first three X’s are in a row are still counted.

**How to do better? -** We will document a formula to give intuition on how we might enumerate all of the different legal game states. Some of the terms in the calculation are unnecessary and are only included to aid with consistency and explanation.

Essentially the way to build the formula for each set of states uses the following logic:

There are nine squares on the board. If we always consider placing n X’s first (where 0<n<6) the first bracketed term in each of our expressions will be of the form (9 CHOOSE n).

The second bracketed term will capture the number of O’s we are placing and will be of the form: (9-n CHOOSE k) where k is the number of O’s being placed.

Finally, once we have placed enough X’s or O’s for victories to happen we subtract a term to account for this. 

Placing zero X’s and zero O’s - (9 CHOOSE 0) * (8 CHOOSE 0) = 1  

Placing one X and zero O’s - (9 CHOOSE 1) * (8 CHOOSE 0) = 9   

Placing one X’s and one O - (9 CHOOSE 1) * (8 CHOOSE 1) = 72   

Placing two X’s and one O - (9 CHOOSE 2) * (7 CHOOSE 1) = 252 

Placing two X’s and two O’s - (9 CHOOSE 2) * (7 CHOOSE 2) = 756

Placing three X’s and two O’s - (9 CHOOSE 3) * (6 CHOOSE 2) = 1260

Placing three X’s and three O’s - (9 CHOOSE 3) * (6 CHOOSE 3) - 8 * (6 CHOOSE 3) = 1520

Placing four X’s and three O’s - (9 CHOOSE 4) * (5 CHOOSE 3) - 8 * (6 CHOOSE 4) = 1140

Placing four X’s and four O’s - (9 CHOOSE 4) * (5 CHOOSE 4) - 8 * (6 CHOOSE 4)*2 = 390 

Placing five X’s and four O’s - (9 CHOOSE 5) * (4 CHOOSE 4) - 8 * (6 CHOOSE 5) = 78 

Summing all of these states gives 5,478 possible legal states for the game. In other reference material, you may see the figure stated as 5,477 which discounts the empty board that we have counted.

**Symmetry -** Note, we have not considered that fundamentally many states are equivalent up to symmetry. For example, the 9 choices for placing one X and zero O’s can be derived by applying rotations to three states - an X in a corner, an X in the middle spot, and an X in a middle edge spot. Therefore instead of 9 states, we would only count 3.
