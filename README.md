# Prodigy_Trackcode_TaskNumber_1
# Caesar Cipher Program
def encrypt(text, shift):
    result = ""
    for char in text:
        if char.isalpha():
            base = ord('A') if char.isupper() else ord('a')
            result += chr((ord(char) - base + shift) % 26 + base)
        else:
            result += char
    return result
def decrypt(text, shift):
    return encrypt(text, -shift)
# Main program
print("Caesar Cipher Encryption and Decryption")
choice = input("Type 'e' to encrypt or 'd' to decrypt: ").lower()
message = input("Enter your message: ")
shift = int(input("Enter shift value: "))
if choice == 'e':
    encrypted_text = encrypt(message, shift)
    print("Encrypted Message:", encrypted_text)
elif choice == 'd':
    decrypted_text = decrypt(message, shift)
    print("Decrypted Message:", decrypted_text)
else:
    print("Invalid choice. Please enter 'e' or 'd'.")
