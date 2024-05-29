


# Hard Level Python Interview Questions

## 1. Two Sum

**Question**
Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

**Test Case**
- Input: `nums = [2,7,11,15], target = 9`
- Output: `[0,1]`

**Explanation**
In this example, `nums[0] + nums[1] = 2 + 7 = 9`, so the output is `[0,1]`.

**Solution Explanation**
We can use a dictionary to store the indices of numbers we have seen so far. For each number in the array, we check if the complement (target - current number) exists in the dictionary. If it does, we return the indices of the current number and its complement. If not, we add the current number to the dictionary and continue.

```python
def two_sum(nums, target):
    num_map = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in num_map:
            return [num_map[complement], i]
        num_map[num] = i
```

## 2. Longest Substring Without Repeating Characters

**Question**
Given a string `s`, find the length of the longest substring without repeating characters.

**Test Case**
- Input: `s = "abcabcbb"`
- Output: `3`

**Explanation**
In this example, the longest substring without repeating characters is `"abc"`, which has a length of `3`.

**Solution Explanation**
We can use a sliding window approach to find the longest substring without repeating characters. We maintain a dictionary to store the index of the last occurrence of each character. We also maintain two pointers `start` and `end` to define the current substring. As we iterate through the string, if we encounter a character that is already in the dictionary, we update the `start` pointer to the next index after the last occurrence of that character. We update the dictionary with the current index of the character. At each step, we update the maximum length of the substring.

```python
def length_of_longest_substring(s):
    char_map = {}
    start = 0
    max_length = 0
    for end in range(len(s)):
        if s[end] in char_map and char_map[s[end]] >= start:
            start = char_map[s[end]] + 1
        char_map[s[end]] = end
        max_length = max(max_length, end - start + 1)
    return max_length
```    

**Test cases:**
```python
print(length_of_longest_substring("abcabcbb"))  # Output: 3
print(length_of_longest_substring("bbbbb"))     # Output: 1
print(length_of_longest_substring("pwwkew"))    # Output: 3
print(length_of_longest_substring(""))          # Output: 0
```

## 3. Merge Intervals

**Question**
Given a collection of intervals, merge all overlapping intervals.

**Test Case**
- Input: `intervals = [[1,3],[2,6],[8,10],[15,18]]`
- Output: `[[1,6],[8,10],[15,18]]`

**Explanation**
In this example, the intervals `[1,3]` and `[2,6]` overlap, so they should be merged into `[1,6]`.

**Solution Explanation**
To merge overlapping intervals, we first sort the intervals based on their start times. Then, we iterate through the sorted intervals and merge overlapping intervals by comparing the end time of the current interval with the start time of the next interval. If there is an overlap, we merge the intervals by updating the end time of the current interval. If there is no overlap, we add the current interval to the result and update the current interval to the next interval.

```python
def merge_intervals(intervals):
    if not intervals:
        return []
    intervals.sort(key=lambda x: x[0])
    merged = [intervals[0]]
    for interval in intervals[1:]:
        if interval[0] <= merged[-1][1]:
            merged[-1][1] = max(merged[-1][1], interval[1])
        else:
            merged.append(interval)
    return merged
```

**Test cases:**
```python
print(merge_intervals([[1,3],[2,6],[8,10],[15,18]]))  # Output: [[1, 6], [8, 10], [15, 18]]
print(merge_intervals([[1,4],[4,5]]))                 # Output: [[1, 5]]
print(merge_intervals([[1,4],[0,2],[3,5]]))           # Output: [[0, 5]]
```

## 4. Top K Frequent Elements

**Question**
Given an integer array `nums` and an integer `k`, return the `k` most frequent elements. You may return the answer in any order.

**Test Case**
- Input: `nums = [1,1,1,2,2,3], k = 2`
- Output: `[1,2]`

**Explanation**
In this example, the two most frequent elements are `1` and `2`.

**Solution Explanation**
To find the `k` most frequent elements, we first count the frequency of each element using a dictionary. Then, we create a list of tuples where each tuple contains the element and its frequency. We sort this list based on the frequency in descending order. Finally, we extract the first `k` elements from the sorted list and return their values.

```python
def top_k_frequent(nums, k):
    freq_map = {}
    for num in nums:
        freq_map[num] = freq_map.get(num, 0) + 1
    sorted_freq = sorted(freq_map.items(), key=lambda x: x[1], reverse=True)
    return [num for num, _ in sorted_freq[:k]]
```

**Test cases:**
```python
print(top_k_frequent([1,1,1,2,2,3], 2))  # Output: [1, 2]
print(top_k_frequent([1], 1))            # Output: [1]
print(top_k_frequent([1,2,3,4,4,4,5,5,5], 3))  # Output: [4, 5, 1] (or [4, 5, 2] or [4, 5, 3])
```

## 5 .Rotate Array

**Question**
Given an array `nums` and an integer `k`, rotate the array to the right by `k` steps.

**Test Case**
- Input: `nums = [1,2,3,4,5,6,7], k = 3`
- Output: `[5,6,7,1,2,3,4]`

**Explanation**
In this example, after rotating the array to the right by 3 steps, the array becomes `[5,6,7,1,2,3,4]`.

**Solution Explanation**
To rotate the array to the right by `k` steps, we reverse the entire array, then reverse the first `k` elements, and finally reverse the rest of the elements. This effectively rotates the array to the right by `k` steps.

```python
def rotate(nums, k):
    k %= len(nums)
    nums.reverse()
    nums[:k] = reversed(nums[:k])
    nums[k:] = reversed(nums[k:])
```

**Test cases:**
```python
nums1 = [1,2,3,4,5,6,7]
rotate(nums1, 3)
print(nums1)  # Output: [5,6,7,1,2,3,4]

nums2 = [-1,-100,3,99]
rotate(nums2, 2)
print(nums2)  # Output: [3,99,-1,-100]

nums3 = [1,2]
rotate(nums3, 3)
print(nums3)  # Output: [2,1]
```

## 6. Minimum Window Substring

**Question**
Given two strings `s` and `t`, return the minimum window in `s` which contains all the characters in `t`. If there is no such window in `s` that covers all characters in `t`, return an empty string `""`.

**Test Case**
- Input: `s = "ADOBECODEBANC", t = "ABC"`
- Output: `"BANC"`

**Explanation**
In this example, the minimum window substring that contains all characters from string `t` is `"BANC"`. The substring starts at index 9 (character 'B') and ends at index 12 (character 'C') in the input string `s = "ADOBECODEBANC"`. This substring includes all characters 'A', 'B', and 'C' from string `t = "ABC"` in the correct order.

**Solution Explanation**
We can use a sliding window approach to find the minimum window substring. We maintain two pointers, `left` and `right`, to define the current window. We also maintain a dictionary `t_count` to store the count of characters in string `t`. As we expand the window by moving the `right` pointer, we decrease the count of the character in `t_count`. When all characters in `t` are found in the current window, we try to shrink the window from the left to minimize its size while still maintaining all characters from `t`. We update the minimum window size and indices as we shrink the window.

```python
def min_window(s, t):
    if not s or not t:
        return ""
    
    t_count = {}
    for char in t:
        t_count[char] = t_count.get(char, 0) + 1
    
    required_chars = len(t_count)
    left, right = 0, 0
    min_window_size = float("inf")
    min_window_start = 0
    char_count = {}
    
    while right < len(s):
        char = s[right]
        char_count[char] = char_count.get(char, 0) + 1
        if char in t_count and char_count[char] == t_count[char]:
            required_chars -= 1
        
        while required_chars == 0:
            if right - left + 1 < min_window_size:
                min_window_size = right - left + 1
                min_window_start = left
            
            char_left = s[left]
            char_count[char_left] -= 1
            if char_left in t_count and char_count[char_left] < t_count[char_left]:
                required_chars += 1
            
            left += 1
        
        right += 1
    
    return "" if min_window_size == float("inf") else s[min_window_start:min_window_start+min_window_size]
```
**Test cases:**
```python
print(min_window("ADOBECODEBANC", "ABC"))  # Output: "BANC"
print(min_window("a", "a"))                # Output: "a"
print(min_window("a", "aa"))               # Output: ""
```

