# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.


# My Answer

Hearing of such an algorithm would make me quite skeptical at first. Skeptical enough for me to believe that this algorithm doesn't actually exist.

To verify my claim, I would put the algorithm through some rigorous testing to see if I can either make it break or show any runtimes that would suggest its runtime is greater than O(n). I would run it through various unit tests with all sorts of data types and different combinations of data. And I would come up with as many property tests as I could to verify it all as well. Comparing it against other fast algorithms and graphing the results would also be something to look at - trying to deduce if anything looks suspicious. If the algorithm were truly linear, I would expect to see a graph resemble a linear trend and be under other sorting algorithms. I would also expect to see similar runtimes if two input sizes are similar (for example, the runtime for an input size of 1,000 would be similar to the runtime with an input of 1,100).

Those are all the concrete ways to try and see if the algorithm truly is linear, however, let's consider some other things conceptually. In order for any sorting algorithm to make decisions, it needs to go through and check *at least* every element in the array - otherwise we wouldn't be able to confirm whether the list is sorted or not.

Now consider this linear-runtime algorithm. This algorithm would need to be what is a called a "comparison-based" algorithm, since you could plug in any unsorted list and it will sort it. Nothing about the list is known, so we will need to compare every element. In the lecture slides, we talk about dividing a comparison-based sorting algorithm into a binary tree where every node is a "choice point." Typically the height of a tree like this is $log(n!)$, where the leaves are all possible permutation of the original list, meaning it will take a complexity of $log(n!)$ (which simplifies to $nlogn$ according to Stirling's approximation) to find the correct sorted list. This is true for *all* comparison-based sorting algorithms, just like our supposed linear algorithm. 

In summary, the worst-case runtime for a comparison-based algorithm is $\Omega(nlogn)$. This means a linear algorithm that is being suggested is likely not truly linear, or it is not a comparison-based algorithm.


# Sources

- Lecture Slides about the sorting problem

# Plagiarism Acknowledgement

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
