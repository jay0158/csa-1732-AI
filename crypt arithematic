import itertools

def solve_crypt_arithmetic():
    # Define the puzzle: SEND + MORE = MONEY
    words = ['SEND', 'MORE']
    result = 'MONEY'
    
    # Extract unique characters
    unique_chars = set(''.join(words) + result)
    assert len(unique_chars) <= 10, "Too many unique characters"
    
    # Create a list of characters
    chars = list(unique_chars)
    
    # Create a function to translate letters to digits
    def to_number(word, char_to_digit):
        return int(''.join(str(char_to_digit[char]) for char in word))
    
    # Iterate over all possible digit permutations
    for perm in itertools.permutations(range(10), len(chars)):
        char_to_digit = dict(zip(chars, perm))
        
        # Check if the leading characters are non-zero
        if any(char_to_digit[word[0]] == 0 for word in words + [result]):
            continue
        
        # Calculate the numbers
        num1 = to_number(words[0], char_to_digit)
        num2 = to_number(words[1], char_to_digit)
        res = to_number(result, char_to_digit)
        
        # Check if the equation is satisfied
        if num1 + num2 == res:
            print(f"Solution found: {words[0]} + {words[1]} = {result}")
            for char, digit in char_to_digit.items():
                print(f"{char} = {digit}")
            return char_to_digit
    
    print("No solution found")
    return None

# Solve the puzzle
solve_crypt_arithmetic()
