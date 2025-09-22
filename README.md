## EX: 8 IMPLEMENTATION OF ADVANCED ENCRYPTION STANDARD

## AIM:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

## ALGORITHM:
1.	Get the input plaintext and key from the user.
2.	Treat the plaintext as a single block of characters.
3.	Perform XOR operation between each character of plaintext and the corresponding character of the key (key repeats if shorter).
4.	Store the XOR result as the ciphertext.
5.	Display the ciphertext in ASCII format.
6.	Perform XOR operation again between the ciphertext and the same key to decrypt.
7.	Store and display the original message as the decrypted text.

## PROGRAM:

```
#include <stdio.h>
#include <string.h>

void xorEncryptDecrypt(char *text, char *key, char *result) {
    int textLen = strlen(text);
    int keyLen = strlen(key);
    for (int i = 0; i < textLen; i++) {
        result[i] = text[i] ^ key[i % keyLen];
    }
    result[textLen] = '\0';
}

int main() {
    char plaintext[256], key[256], ciphertext[256], decrypted[256];

    printf("Enter the plaintext : ");
    fgets(plaintext, sizeof(plaintext), stdin);
    plaintext[strcspn(plaintext, "\n")] = '\0';

    printf("Enter the key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';

    xorEncryptDecrypt(plaintext, key, ciphertext);

    printf("Ciphertext (ASCII values): ");
    for (int i = 0; i < strlen(ciphertext); i++) {
        printf("%d ", (unsigned char)ciphertext[i]);
    }
    printf("\n");

    xorEncryptDecrypt(ciphertext, key, decrypted);
    printf("Decrypted text: %s\n", decrypted);

    return 0;
}

```
## OUTPUT:

<img width="702" height="202" alt="Screenshot 2025-09-22 143313" src="https://github.com/user-attachments/assets/8b8dc58c-f2ce-46e9-b51a-89891c93e0e6" />

## RESULT:
Hence, Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption is done successfully.
