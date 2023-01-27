# Valid_Parentheses
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

class Solution:
    def is_valid_parentheses(self, s:str) - > bool
        # create a dictionary that will contain close ")" as key and open "(" 
        brackets = {')':'(', ']':'[', '}':'{'}
        
        # create a stack in list format to store char if its open 
        stack = []
        
        # iterate to your string given and check if char is in your dictionary if yes, the char is close else the char is open then we can append that to stack
        for char in s:
            if char in brackets:
                
                # pop the top element of the stack and store it in a variable, store any char as placeholder if stack is empty
                top_char = stack.pop() if stack else '#'\
                #compare top_char to your char's value inside your brackets dictionary and see if they make a pair, if they dont match return False
                if top_char != brackets[char]:
                    return False
                
            else:
                 stack.append(char)
                 
       #returns whether the stack is empty or not
       return Not stack 
