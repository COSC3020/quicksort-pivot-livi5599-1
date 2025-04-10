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

When considering the median-to-three method for finding a pivot, I did a test on an array of five elements.  I selected three elements, and I ordered them in every way possible while keeping track of how many times the median element was placed in the middle, where it should be.  After doing this, I determined that there was a probability of 1/3 for this case.  Using this knowledge, I believe the average case is more likely to find a good pivot since 1/2 > 1/3.

-----

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models.  All of the work is my own, except where stated otherwise.  I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
