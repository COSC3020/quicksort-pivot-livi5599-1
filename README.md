# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

-----

A "good pivot" is a pivot that is placed in the middle range of an array.  According to the lecture slide on the intuition of the average case of quicksort, the probability that the randomly selected element is an element in the middle portion of the array is 1/2.

When considering the median-to-three method for finding a pivot, each of the three chosen elements have a chance of being a good pivot, too small, or too large.  If a good pivot is represented by M (for median), one that is too small represented by S, and one that is too large represented by L, these are the different ways the three elements chosen from the array could be represented:

MMM,
SSS,
LLL,
MSS,
MMS,
MLL,
SLL,
SSL,
LSS,
SLM

These combinations each have different probabilities, as the probability of an element falling in the middle portion of the array is 1/2, and the probability of an element falling in the left/right portion of the array is 1/4.  These chances come from the fact that the middle portion of the array is twice as large as the left/right portions.

Considering the chances given above, these are the probabilities of each of the combinations occuring:

MMM = 1/2 * 1/2 * 1/2 = 1/8
SSS = 1/4 * 1/4 * 1/4 = 1/64
LLL = 1/4 * 1/4 * 1/4 = 1/64
MSS = 1/2 * 1/4 * 1/4 = 1/32
MMS = 1/2 * 1/2 * 1/4 = 1/16
MML = 1/2 * 1/2 * 1/4 = 1/16
MLL = 1/2 * 1/4 * 1/4 = 1/32
SLL = 1/4 * 1/4 * 1/4 = 1/64
SSL = 1/4 * 1/4 * 1/4 = 1/64
SLM = 1/4 * 1/4 * 1/2 = 1/32

Considering the combinations and all the different ways they can occur and how that effects their probabilities:

1 MMM -> 1/8
1 SSS -> 1/64
1 LLL -> 1/64
3 MSS -> 3/32
3 MMS -> 3/16
3 MML -> 3/16
3 MLL -> 3/32
3 SLL -> 3/64
3 SSL -> 3/64
6 SLM -> 6/32

Now, adding the probabilities that result in a good pivot in proper position:

1/8 + 3/16 + 3/16 = 11/16 = 68.75%

This means the median-to-three method has a 68.75% chance to pick a good pivot, which shows that this method is 18.75% more likely to pick a good pivot than the average input method.

-----

I received help from Khan Academy, ChatGPT, and Ali.  I found a quicksort analysis on Khan Academy.  A portion of this analysis briefly talked about the median-to-three method.  I gave that portion of the analysis to ChatGPT, as I was unsure where the given fractions/percentages were coming from, and ChatGPT explained that they came from the number of possible ways to order a set of numbers.  This gave me the idea of building the table above.  ChatGPT also hinted to me that I need to consider more of what is going on with the values of the elements in the array, not just how the possible pivot elements are ordered, which led me to my answer.  And Ali helped explain why each combination has a different probability when considering the fact that the array is divided into quarters, not thirds as I had originally thought.  After his brief explanation, I was able to go through the process above and come to my conclusion.

Khan Academy source: https://www.khanacademy.org/computing/computer-science/algorithms/quick-sort/a/analysis-of-quicksort

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models.  All of the work is my own, except where stated otherwise.  I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
