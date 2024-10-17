# Mystery Function

What does the `mystery()` function in the following piece of code do? Add your
answer to this markdown file.

```javascript
function mystery(a) {
    if(a.length == 1) return a[0];
    var foo = mystery(a.slice(1, a.length))
    if(foo > a[0]) return foo;
    else return a[0];
}
```

This function finds the largest value in a given array, my reasoning is below.

This function takes an input array 'a' and performs the following:
1. If the array 'a' has one item, it will return that entry as its result.
2. If the array has more than one item, the mystery() function calls itself recursively, but this time, from the second item in the array, a[1] to the end of the array. This is done by the a.slice() method, which creates a new array which begins at the second item a[1] and continues to the end of the array, not overflowing because .slice() does not include the end entry. This will go back to step 1. The eventual result of this recursion will be passed to the foo variable. The foo variable will either be the initial item in the array at that point, or take another slice of the array.
3. After mystery has run, the first item in the array is compared to foo. If it is greater, it is then returned. If not, a[0] is returned.
4. Effectively, what this means, is that the largest item in the array is eventually returned. The recursive nature of the function means that it goes to the very end of the array, as the array will only be of a.length() = 1 when there is only one item, which will then be passed backward, each time being compared to the first entry, working its way through the array and determining which is larger. Until eventually, the largest value in the array is returned.

I only used one external source for this assignment. I used this website https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice to figure out what the slice function did. The rest was just logically going through the function to determine what it did.

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
