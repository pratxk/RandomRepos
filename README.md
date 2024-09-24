# RandomRepos


#code for longest subsequence array element:

To solve the problem of finding the length of the longest strictly increasing subarray, we can simplify your approach. Instead of using nested loops to generate all subarrays, we can iterate through the array and keep track of the length of the current increasing sequence. 

Here’s a corrected and simplified version of your code:

```python
testCase = int(input())

for _ in range(testCase):
    n = int(input())
    arr = list(map(int, input().split()))

    # Variables to keep track of the maximum length and current length
    max_length = 1
    current_length = 1

    for i in range(1, n):
        if arr[i] > arr[i - 1]:  # Check if current element is greater than previous
            current_length += 1  # Increase current increasing length
        else:
            max_length = max(max_length, current_length)  # Update max_length if needed
            current_length = 1  # Reset current length for the next increasing sequence

    # Final check in case the longest sequence is at the end of the array
    max_length = max(max_length, current_length)

    print(max_length)
```

### Explanation:
1. **Input Handling**: We read the number of test cases and then the size of each array and the array itself.
2. **Tracking Lengths**: We initialize `max_length` to 1 (minimum length for any subarray) and `current_length` to 1.
3. **Single Pass**: We iterate through the array starting from the second element. If the current element is greater than the previous one, we increase the `current_length`. If not, we compare `current_length` to `max_length` and reset `current_length` to 1.
4. **Final Comparison**: After the loop, we do a final check to ensure that we account for cases where the longest increasing subarray ends at the last element.
5. **Output**: We print the length of the longest increasing subarray for each test case.

This approach runs in O(n) time for each test case, making it efficient and straightforward.
