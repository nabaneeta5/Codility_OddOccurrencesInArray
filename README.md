# Codility_OddOccurrencesInArray
Find value that occurs in odd number of elements.

# Task description
A non-empty array A consisting of N integers is given. The array contains an odd number of elements, and each element of the array can be paired with another element that has the same value, except for one element that is left unpaired.

# Link Details
[trainingSEJ89B-JA5](https://app.codility.com/demo/results/trainingSEJ89B-JA5/)

# Programming Language
Java SE 11

# Solution Code

```
import java.util.*;
import java.util.stream.Collectors;

class Solution {
    public int solution(int[] A) {
        // write your code in Java SE 11

        Map<Integer, Long> counts =
            Arrays.stream(A).boxed().collect(Collectors.groupingBy(e -> e, Collectors.counting()));
        for(Map.Entry<Integer, Long> entry : counts.entrySet()){
            if(entry.getValue().intValue()%2!=0){
                return entry.getKey();
            }
             
        }
    
    return 0;
    }
}

```

