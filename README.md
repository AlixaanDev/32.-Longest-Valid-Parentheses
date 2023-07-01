# 32.-Longest-Valid-Parentheses
class Solution:
    def longestValidParentheses(self, s: str) -> int:
        pos=[]
        left=[]
        index=-1
        max_num=0
        max_list=[0]
        i = 0
        while i < len(s):
            if s[i] == '(':    
                left.append(0)
                pos.append(i)
            elif s[i] == ')' and len(pos) != 0:
                left[pos.pop()] = 1
                left.append(1)
            elif s[i] == ')' and len(pos) == 0:
                left.append(0)
            i += 1
        for i in left:
            if i == 1:
                max_num += 1
            if i == 0:
                max_list.append(max_num)
                max_num = 0
            max_list.append(max_num)
        return max(max_list)

                    
