# leet-day66

# K Weakest Rows in a Matrix

Given an `m x n` binary matrix `mat` of 1's (representing soldiers) and 0's (representing civilians) where soldiers are positioned in front of civilians, find and return the indices of the k weakest rows in the matrix. The rows are ordered from weakest to strongest.

## Approach

To solve this problem, we can follow these steps:

1. Create a vector of pairs, where each pair contains two elements: the number of soldiers in a row and the row index.

2. Traverse through each row in the matrix and count the number of soldiers in that row. Store this information in the vector of pairs.

3. Sort the vector of pairs based on the number of soldiers (in ascending order) and then by row index (in ascending order). This will ensure that rows with fewer soldiers come first, and in case of a tie, rows with lower row indexes come first.

4. Create a result vector to store the row indexes of the weakest rows.

5. Iterate through the sorted vector of pairs and add the row indexes to the result vector until the size of the result vector reaches 'k'.

6. Return the result vector as the answer.

## Complexity Analysis

The time complexity of this solution is dominated by the sorting step, which has a time complexity of O(m * log(m)), where m is the number of rows in the matrix.

The space complexity is O(m) as we use a vector of pairs to store the soldiers' count and row index.

