import re

def check_password_strength(password):
    strength = "Weak"

    if len(password) >= 8:
        if re.search("[a-z]", password) and re.search("[A-Z]", password):
            if re.search("[0-9]", password) and re.search("[@#$%^&+=]", password):
                strength = "Strong"
            else:
                strength = "Medium"
        else:
            strength = "Medium"
    else:
        strength = "Weak"

    return strength


# User input
password = input("Enter password: ")

# Check strength
result = check_password_strength(password)

# Output
print("Password Strength:", result)
