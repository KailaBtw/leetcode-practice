# Readme file

## findAllDuplicates function

* Write a function (or static method in the case of Java) that accepts a list of integers and returns a list of only those integers that appear more than once

```{java}
    public static LinkedList<Integer> findAllDuplicates(LinkedList<Integer> list) {
        LinkedList<Integer> ret = new LinkedList<>();
        HashSet<Integer> seen = new HashSet<>();
        HashSet<Integer> duplicates = new HashSet<>();

            for(Integer element : list) {
                if(seen.contains(element)) {
                    //add it to list?
                    if(!duplicates.contains(element)) {
                        ret.add(element);
                        duplicates.add(element); // add to duplicates so we dont have multiple in ret
                    }
                } else {
                    // add to our seen list
                    seen.add(element);
                }
            }
        return ret;
    }
```

## Describe Different Approaches to Solving This Problem

* Describe the two different ways to figure out all of the duplicate values of a list of integers in english. The first solution is the nested loop solution. The second solution is to use a dictionary or a map (similar to the containsPair method we wrote in class. Describe both in as much detail as you can (with no code) and describe the trade-offs between the two solutions.

  * Nested Loop Approach - This approach uses a selectionn search style approach, selecting an element in A and checking all elements after that element, against it. There are also checks to prevent duplicate values in the output array. This approach is O(n^2) in the best case because it will always have to loop over (nearly) all elements, for each element in A.

  * Set/Dictonary Solution - Contains methods are typically an O(n) task, except in the case of hashed data structures. This solution also uses the concept of a mathematical set, which doesn't allow duplicate elements. The contains operation on a hashset/map is also O(1) in most cases. Each value in A, when seen is added to a seen-list, then when we see it a second time we add it to return and to the duplicates (which are the same elements as ret, but have O(1) contains)

