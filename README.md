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

When considering the median-to-three method for finding a pivot, I wrote out all permutations of three elements (e1, e2, and e3, where e1 is the first element, e2 is the middle element, and e3 is the last element).  I created a table, which looks like:

| e1 | e2 | e3 |
| -- | -- | -- |
| 0  | 0  | 0  |
| 0  | 0  | 1  |
| 0  | 1  | 0  |
| 1  | 0  | 0  |
| 1  | 1  | 0  |
| 0  | 1  | 1  |
| 1  | 0  | 1  |
| 1  | 1  | 1  |

1 represents when an element is the median element, and 0 represents when an element is not the median element.

Here are the different combinations e1, e2, and e3:

e1 < e2 < e3
e1 < e3 < e2
e2 < e1 < e3
e2 < e3 < e1
e3 < e1 < e2
e3 < e2 < e1

Looking at the 6 different combinations of the elements, each combination has a 16.67% chance of occuring.  Each element appears as the median 2 out of the 6 combinations, which is 33.33%.  The chance of the median element occuring in the middle portion of the element is 33.33%, as there are three portions to the array (left, middle, right), and an element will be placed in the middle portion 1/3 = 33.33% of the time.  Combining these probabilities, I get 83.33%, which argues that the median-to-three method is 33.33% more likely to pick a good pivot compared to the average input method.

-----

I received help from Khan Academy and ChatGPT.  I found a quicksort analysis on Khan Academy.  A portion of this analysis briefly talked about the median-to-three method.  I gave that portion of the analysis to ChatGPT, as I was unsure where the given fractions/percentages were coming from, and ChatGPT explained that they came from the number of possible ways to order a set of numbers.  This gave me the idea of building the table above.  ChatGPT also hinted to me that I need to consider more of what is going on with the values of the elements in the array, not just how the possible pivot elements are ordered, which led me to my answer.

Khan Academy source: https://www.khanacademy.org/computing/computer-science/algorithms/quick-sort/a/analysis-of-quicksort

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models.  All of the work is my own, except where stated otherwise.  I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
