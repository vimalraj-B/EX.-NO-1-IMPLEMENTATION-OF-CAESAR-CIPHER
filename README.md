# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:

```
#include <stdio.h>
#include <ctype.h>

void caesarCipher(char text[], int shift, char mode[]) {
    if (mode[0] == 'd') { 
        shift = -shift;
    }

    for (int i = 0; text[i] != '\0'; i++) {
        char ch = text[i];

        if (isalpha(ch)) {  
            char base = isupper(ch) ? 'A' : 'a';
            ch = (ch - base + shift + 26) % 26 + base;
        }
        text[i] = ch; 
    }
}

int main() {
    char message[100] = "VIMALRAJ"; 
    int key = 3;

    char encrypted[100];
    char decrypted[100];

    snprintf(encrypted, sizeof(encrypted), "%s", message);
    snprintf(decrypted, sizeof(decrypted), "%s", encrypted);


    caesarCipher(encrypted, key, "encrypt");
  
    caesarCipher(decrypted, key, "decrypt");

    printf("Original : %s\n", message);
    printf("Encrypted: %s\n", encrypted);
    printf("Decrypted: %s\n", decrypted);

    return 0;
}
```

## OUTPUT:

<img width="347" height="278" alt="image" src="https://github.com/user-attachments/assets/327ff2e2-87da-4820-b63e-e5d48bbad229" />


## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
