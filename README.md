# 🚀 Day 27 – Valid Anagram

## 📌 Problem

Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, otherwise return `false`.

An anagram is a word formed by rearranging the letters of another word using all original characters exactly once.

### Example

```python
Input: s = "anagram", t = "nagaram"
Output: True
```

### Example 2

```python
Input: s = "rat", t = "car"
Output: False
```

---

# 💡 Approach – Hash Map / Frequency Counting

We count the frequency of every character in both strings.

### Steps:

* If lengths are different:

  * return `False`
* Store character counts using a dictionary
* Compare frequencies
* If all frequencies match:

  * strings are valid anagrams

---

# ⚙️ Python Solution

```python
class Solution:
    def isAnagram(self, s, t):
        if len(s) != len(t):
            return False

        countS = {}
        countT = {}

        for i in range(len(s)):
            countS[s[i]] = 1 + countS.get(s[i], 0)
            countT[t[i]] = 1 + countT.get(t[i], 0)

        return countS == countT
```

---

# 🧠 Dry Run

Input:

```python
s = "anagram"
t = "nagaram"
```

### Frequency Maps

| Character | Count in s | Count in t |
| --------- | ---------- | ---------- |
| a         | 3          | 3          |
| n         | 1          | 1          |
| g         | 1          | 1          |
| r         | 1          | 1          |
| m         | 1          | 1          |

All frequencies match ✅

Final Answer:

```python
True
```

---

# ⏱️ Complexity Analysis

| Complexity       | Value |
| ---------------- | ----- |
| Time Complexity  | O(n)  |
| Space Complexity | O(1)  |

---

# 🧠 Key Learning

This problem teaches:

* Hashing
* Frequency counting
* Efficient string comparison

Hash maps are extremely useful for character-based problems.

---

# ⚠️ Important Insight

Sorting both strings also works:

```python
sorted(s) == sorted(t)
```

But sorting takes:

```python
O(n log n)
```

Frequency counting is more optimal with:

```python
O(n)
```

---

# 🔗 LeetCode

Valid Anagram – LeetCode #242

---

# 📈 Progress Log

✅ Day 27 of DSA Journey
