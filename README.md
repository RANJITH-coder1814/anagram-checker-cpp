Valid Anagram
Problem Statement

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An anagram is a word formed by rearranging the letters of another word using all the original characters exactly once.

Example
Example 1
Input: s = "anagram", t = "nagaram"
Output: true
Example 2
Input: s = "rat", t = "car"
Output: false
Approach
Check if both strings have the same length.
Use a frequency array of size 26 to count characters.
Increment counts for characters in s.
Decrement counts for characters in t.
If all frequencies become zero, the strings are anagrams.
C++ Solution
class Solution {
public:
    bool isAnagram(string s, string t) {
        if (s.length() != t.length()) {
            return false;
        }

        vector<int> freq(26, 0);

        for (char c : s) {
            freq[c - 'a']++;
        }

        for (char c : t) {
            freq[c - 'a']--;
        }

        for (int count : freq) {
            if (count != 0) {
                return false;
            }
        }

        return true;
    }
};
Time Complexity
O(n)
Space Complexity
O(1)
Topics
String
Hash Table
Counting
Repository Name Ideas
valid-anagram-solution
leetcode-valid-anagram
anagram-checker-cpp
valid-anagram-leetcode-242
readme
Valid Anagram

A simple and efficient C++ solution for the LeetCode 242 - Valid Anagram problem.

Problem Statement

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word formed by rearranging the letters of another word using all the original characters exactly once.

Examples
Example 1
Input: s = "anagram", t = "nagaram"
Output: true
Example 2
Input: s = "rat", t = "car"
Output: false
Approach
First check whether both strings have the same length.
Use a frequency array of size 26.
Count characters from the first string.
Reduce counts using the second string.
If all frequencies become 0, both strings are anagrams.
