"""
LeetCode - 5957
Adding Spaces to a String
"""
"""
#Question

You are given a 0-indexed string s and a 0-indexed integer array spaces that describes the indices in 
the original string where spaces will be added. Each space should be inserted before the character at 
the given index.

For example, given s = "EnjoyYourCoffee" and spaces = [5, 9], we place spaces before 'Y' and 'C', which 
are at indices 5 and 9 respectively. Thus, we obtain "Enjoy Your Coffee".
Return the modified string after the spaces have been added.
"""
"""
#SampleCase 1
Input: s = "LeetcodeHelpsMeLearn", spaces = [8,13,15]
Output: "Leetcode Helps Me Learn"
Explanation: 
The indices 8, 13, and 15 correspond to the underlined characters in "LeetcodeHelpsMeLearn".
We then place spaces before those characters.
"""
"""
#SampleCase 2
Input: s = "icodeinpython", spaces = [1,5,7,9]
Output: "i code in py thon"
Explanation:
The indices 1, 5, 7, and 9 correspond to the underlined characters in "icodeinpython".
We then place spaces before those characters.
"""
"""
#SampleCase 3
Input: s = "spacing", spaces = [0,1,2,3,4,5,6]
Output: " s p a c i n g"
Explanation:
We are also able to place spaces before the first character of the string.
"""
"""
#Constraints
1 <= s.length <= 3 * 105
s consists only of lowercase and uppercase English letters.
1 <= spaces.length <= 3 * 105
0 <= spaces[i] <= s.length - 1
All the values of spaces are strictly increasing.
"""
#Solution
#Time - O(StrLen+SpacesLen)
#Memory - O(StrLen+SpacesLen)

class Solution:
    def addSpaces(self, s: str, spaces: List[int]) -> str:
        Res = ""
        StrLen,LisLen = len(s),len(spaces)
        LisInd,StrInd,AddVal = 0,0,0
        for i in range(StrLen+LisLen):
            if((LisInd < LisLen) and (i == spaces[LisInd]+AddVal)):
                Res += " "
                LisInd += 1
                AddVal += 1
            else:
                Res += s[StrInd]
                StrInd += 1
        return Res