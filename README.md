# Valid-Parentheses-with-Multiple-Types
Check if a string s containing parentheses (), {}, and [] is valid. A string is valid if every opening bracket has a matching closing bracket of the same type, and the brackets close in the correct order (last opened must be closed first).
def isValid(s: str) -> bool:
    stack = []
    mapping = {')': '(', '}': '{', ']': '['}
    for char in s:
        if char in mapping.values():
            stack.append(char)
        elif char in mapping:
            if not stack or stack[-1] != mapping[char]:
                return False
            stack.pop()
    return not stack
s = "[{()}]"
print(isValid(s)) 
