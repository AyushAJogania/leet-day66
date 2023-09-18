# leet-day66

# Set Matrix Zeroes

## Problem Description

Given an `m x n` integer matrix `matrix`, if an element is `0`, set its entire row and column to `0`. You must do it **in place**.

### Example 1:

Input:
```cpp
matrix = [[1,1,1],[1,0,1],[1,1,1]]
```

Output:
```cpp
[[1,0,1],[0,0,0],[1,0,1]]
```

### Example 2:

Input:
```cpp
matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]
```

Output:
```cpp
[[0,0,0,0],[0,4,5,0],[0,3,1,0]]
```

**Note:**

- A straightforward solution using O(mn) space is probably a bad idea.
- A simple improvement uses O(m + n) space, but still not the best solution.
- Could you devise a constant space solution?

## Approach

The problem can be solved efficiently in C++ using constant extra space. We can use the first cell of each row and column as a flag to mark whether that row or column should be zeroed out. Here's a step-by-step explanation of the approach:

1. Initialize two boolean variables, `firstRowZero` and `firstColZero`, to keep track of whether the first row and first column should be zeroed out.

2. Iterate through the first row and first column of the matrix to check if they contain any zeros. Set `firstRowZero` and `firstColZero` accordingly.

3. Use the first cell of each row and column as flags to mark the rows and columns that should be zeroed out. For example, if `matrix[i][j]` is `0`, set `matrix[i][0]` and `matrix[0][j]` to `0`.

4. Iterate through the matrix starting from the second row and second column. If `matrix[i][0]` or `matrix[0][j]` is `0`, set `matrix[i][j]` to `0`.

5. Finally, zero out the first row and/or first column if `firstRowZero` or `firstColZero` is `true`.

## Time Complexity

The time complexity of this solution is O(m * n) because we iterate through the entire matrix once.

## Space Complexity

The space complexity is O(1) since we use only a constant amount of extra space.
