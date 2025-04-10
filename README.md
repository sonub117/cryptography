def caesar_cipher_decrypt(ciphertext, shift):
    decrypted_text = ''
    for char in ciphertext:
        if char.isalpha():
            shift_base = 65 if char.isupper() else 97
            decrypted_text += chr((ord(char) - shift_base - shift) % 26 + shift_base)
        else:
            decrypted_text += char
    return decrypted_text

def brute_force_caesar_cipher(ciphertext):
    for shift in range(26):
        decrypted_text = caesar_cipher_decrypt(ciphertext, shift)
        print(f'Shift {shift}: {decrypted_text}')

if __name__ == '__main__':
    # Example ciphertext (encrypted with a Caesar cipher with shift 3)
    ciphertext = 'Khoor, Zruog!'
    print('Attempting to decrypt using brute-force approach:\n')
    brute_force_caesar_cipher(ciphertext)
