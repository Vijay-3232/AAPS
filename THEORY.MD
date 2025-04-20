## **✅ Algorithm:**
1. **Build Prefix Sum Array:**
   1. Create a new array prefix[] where:

prefix[i] = arr[0] + arr[1] + ... + arr[i]

1. In other words:
prefix[0] = arr[0]
prefix[i] = prefix[i-1] + arr[i]

1. **To find sum of elements in range [L, R]:**
   1. If L == 0 → return prefix[R]
   1. Else → return prefix[R] - prefix[L-1]

## **💻 Java Program:**
java

public class PrefixSumRange {

`    `// Function to build prefix sum array

`    `public static int[] buildPrefixSum(int[] arr) {

`        `int[] prefix = new int[arr.length];

`        `prefix[0] = arr[0];

`        `for (int i = 1; i < arr.length; i++) {

`            `prefix[i] = prefix[i - 1] + arr[i];

`        `}

`        `return prefix;

`    `}


`    `// Function to get sum from L to R

`    `public static int rangeSum(int[] prefix, int L, int R) {

`        `if (L == 0) return prefix[R];

`        `return prefix[R] - prefix[L - 1];

`    `}


`    `public static void main(String[] args) {

`        `int[] arr = {2, 4, 1, 6, 3, 8};

`        `int[] prefix = buildPrefixSum(arr);


`        `int L = 1;

`        `int R = 4;

`        `int sum = rangeSum(prefix, L, R);


`        `System.out.println("Sum from index " + L + " to " + R + " = " + sum);

`    `}

}


## **🧠 Dry Run / Example:**
Let arr = [2, 4, 1, 6, 3, 8]

- Prefix sum array:
  ` `prefix = [2, 6, 7, 13, 16, 24]
- For range L = 1, R = 4:
  - prefix[4] - prefix[0] = 16 - 2 = 14

✅ Elements from index 1 to 4 are: 4 + 1 + 6 + 3 = 14

## **⏱️ Time & Space Complexity**

|**Operation**|**Complexity**|
| :-: | :-: |
|Build Prefix|O(n)|
|Query Sum [L,R]|O(1)|
|Space (prefix)|O(n)|

Very efficient for **multiple queries**.


