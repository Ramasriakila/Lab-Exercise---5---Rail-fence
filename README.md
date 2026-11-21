# Lab-Exercise---5---Rail-fence
## Aim
To implement the Rail Fence Cipher technique for encryption and decryption of a given plaintext.

## Procedure
1.Start the program.

2.Get the plaintext and number of rails as input from the user.

3.Arrange the plaintext characters in a zigzag pattern across the specified number of rails.

4.Read the characters row by row to obtain the encrypted text.

5.For decryption, reconstruct the zigzag pattern.

6.Read the characters to obtain the original plaintext.

7.Display the encrypted and decrypted messages.

8.Stop the program.

## program
```
def rail_fence_encrypt(text, rails):
    if rails == 1:
        return text

    # Create the 2D matrix filled with '\n'
    fence = [['\n' for _ in range(len(text))] for _ in range(rails)]

    row = 0
    direction = 1  # 1 for downward, -1 for upward

    # Place characters in the zig-zag pattern
    for col, char in enumerate(text):
        fence[row][col] = char

        if row == 0:
            direction = 1
        elif row == rails - 1:
            direction = -1

        row += direction

    # Read row by row to construct ciphertext
    encrypted_text = ""
    for row in fence:
        for char in row:
            if char != '\n':
                encrypted_text += char

    return encrypted_text


message = input("Enter the plaintext: ")
rails = int(input("Enter the number of rails: "))

ciphertext = rail_fence_encrypt(message, rails)

print("Plaintext:", message)
print("Encrypted text:", ciphertext)
```

## output

<img width="1417" height="847" alt="image" src="https://github.com/user-attachments/assets/fd9107f9-9d0d-460f-81a4-55efed523734" />

## Result

Thus, the Rail Fence Cipher algorithm was successfully implemented, and the encryption and decryption of the given plaintext were performed successfully.
