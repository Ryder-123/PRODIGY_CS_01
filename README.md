# Caesar Cipher Tool 🔐

A simple Python program to encrypt and decrypt messages using the classic Caesar Cipher algorithm.

## 💡 What is Caesar Cipher?

The Caesar Cipher is a basic encryption technique where each letter in a message is shifted by a fixed number of places down or up the alphabet.

## 📌 Features

- Encrypts plain text messages
- Decrypts encrypted messages
- Handles both uppercase and lowercase letters
- Ignores and retains punctuation, numbers, and spaces

## 🖥️ Usage

1. Clone the repository:





def caesar_encrypt(text, shift):
    result = ""
    for char in text:
        if char.isalpha():
            base = ord('A') if char.isupper() else ord('a')
            shifted = (ord(char) - base + shift) % 26 + base
            result += chr(shifted)
        else:
            result += char
    return result

def caesar_decrypt(text, shift):
    return caesar_encrypt(text, -shift)

def main():
    print("=== Caesar Cipher Tool ===")
    choice = input("Do you want to (E)ncrypt or (D)ecrypt?: ").strip().lower()
    message = input("Enter your message: ")
    try:
        shift = int(input("Enter shift value (number): "))
    except ValueError:
        print("Shift must be an integer!")
        return

    if choice == 'e':
        encrypted = caesar_encrypt(message, shift)
        print("Encrypted message:", encrypted)
    elif choice == 'd':
        decrypted = caesar_decrypt(message, shift)
        print("Decrypted message:", decrypted)
    else:
        print("Invalid choice. Please select 'E' or 'D'.")

if __name__ == "__main__":
    main()
