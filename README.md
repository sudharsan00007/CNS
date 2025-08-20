## EX. NO: 1 : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


PROGRAM :-
```
#include <stdio.h>
#include <stdlib.h>

void caesarEncrypt(char *text, int key) {
    for (int i = 0; text[i] != '\0'; i++) {
        char c = text[i];
        if (c >= 'A' && c <= 'Z') {
            text[i] = ((c - 'A' + key) % 26 + 26) % 26 + 'A';
        }
        else if (c >= 'a' && c <= 'z') {
            text[i] = ((c - 'a' + key) % 26 + 26) % 26 + 'a';
        }
    }
}

void caesarDecrypt(char *text, int key) {
    caesarEncrypt(text, -key);
}

int main() {
    char message[100]; 
    int key;

    printf("Enter the message to encrypt: ");
    fgets(message, sizeof(message), stdin); 
    printf("Enter the Caesar Cipher key (an integer): ");
    scanf("%d", &key); 

    caesarEncrypt(message, key);
    printf("Encrypted Message: %s\n", message);

    caesarDecrypt(message, key);
    printf("Decrypted Message: %s\n", message);

    return 0;
}
```




OUTPUT :-

<img width="816" height="266" alt="image" src="https://github.com/user-attachments/assets/1cb752a0-504a-4e5f-abc7-46bf9c3123c8" />
