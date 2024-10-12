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

To verify my claim, I would put the algorithm through some rigorous testing to see if I can either make it break or show any runtimes that would suggest its runtime is greater than O(n). I would run it through various unit tests with all sorts of data types and different combinations of data. And I would come up with as many property tests as I could to verify it all as well. Comparing it against other fast algorithms and graphing the results would also be something to look at - trying to deduce if anything looks suspicious.

Those are all the concrete ways to try and see if the algorithm truly is linear, however, let's consider some other things conceptually. In order for any sorting algorithm to make decisions, it needs to go through and check *at least* every element in the array - otherwise we wouldn't be able to confirm whether the list is sorted or not. We need to be able to "see" the data. 

Now consider this linear-runtime algorithm. As the algorithm goes along and checks some elements, there are two different parts of the array. The part we have "seen" and the part we have "not seen." If this algorithm is linear and is sorting elements as it goes, it is placing elements blind. The odds of misplacing elements are (almost) gaurunteed because there is no way to know what is coming up next - the algorithm is essentially forced to guess where to put the elements. (There is a very small possibility where it could correctly sort an array, but this would be an incredibly rare event depending on the size of the array - especially if the input is large). Because of this, I would highly doubt that the algorithm is actually linear.


# Sources

- None

# Plagiarism Acknowledgement

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
