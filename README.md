# Encrypt-and-Decrypt-Text
This program allows users to encrypt and decrypt text using the Caesar Cipher algorithm. 
def caesar_cipher(text, shift):
    """Encrypts or decrypts a text using the Caesar Cipher algorithm.

    Args:
        text: The text to be encrypted or decrypted.
        shift: The number of positions to shift the letters.

    Returns:
        The encrypted or decrypted text.
    """

    result = ""
    for char in text:
        if char.isalpha():
            if char.isupper():
                char = chr((ord(char) + shift - 65) % 26 + 65)
            else:
                char = chr((ord(char) + shift - 97) % 26 + 97)
        result += char
    return result

def main():
    while True:
        choice = input("Choose an option:\n1. Encrypt\n2. Decrypt\n3. Exit\n")
        if choice not in ["1", "2", "3"]:
            print("Invalid choice. Please try again.")
            continue

        if choice == "3":
            break

        text = input("Enter the text: ")
        shift = int(input("Enter the shift value: "))

        if choice == "1":
            encrypted_text = caesar_cipher(text, shift)
            print("Encrypted text:", encrypted_text)
        elif choice == "2":
            decrypted_text = caesar_cipher(text, -shift)
            print("Decrypted text:", decrypted_text)

if _name_ == "_main_":
    main()
