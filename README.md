# password-checker
import re

password = input("Enter your password: ")

length = len(password) >= 8
uppercase = re.search(r"[A-Z]", password)
lowercase = re.search(r"[a-z]", password)
numbers = re.search(r"[0-9]", password)
symbols = re.search(r"[!@#$%^&*()_+-=]", password)

score = length + bool(uppercase) + bool(lowercase) + bool(numbers) + bool(symbols)

if score == 5:
    print("Strong Password 💪")
elif score == 3 or score == 4:
    print("Medium Password 🙂")
else:
    print("Weak Password ⚠")
