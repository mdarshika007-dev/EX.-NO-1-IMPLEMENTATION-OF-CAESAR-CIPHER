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
~~~
#include <stdio.h>
#include <string.h>

int main()
{
    char text[100];
    char encrypted[100];
    char decrypted[100];
    int key, i;

    printf("Enter the plain text: ");
    fgets(text, sizeof(text), stdin);

    printf("Enter the key value: ");
    scanf("%d", &key);

    /* Encryption */
    for (i = 0; text[i] != '\0'; i++)
    {
        if (text[i] >= 'A' && text[i] <= 'Z')
        {
            encrypted[i] = ((text[i] - 'A' + key) % 26) + 'A';
        }
        else if (text[i] >= 'a' && text[i] <= 'z')
        {
            encrypted[i] = ((text[i] - 'a' + key) % 26) + 'a';
        }
        else
        {
            encrypted[i] = text[i];
        }
    }

    encrypted[i] = '\0';

    /* Decryption */
    for (i = 0; encrypted[i] != '\0'; i++)
    {
        if (encrypted[i] >= 'A' && encrypted[i] <= 'Z')
        {
            decrypted[i] = ((encrypted[i] - 'A' - key + 26) % 26) + 'A';
        }
        else if (encrypted[i] >= 'a' && encrypted[i] <= 'z')
        {
            decrypted[i] = ((encrypted[i] - 'a' - key + 26) % 26) + 'a';
        }
        else
        {
            decrypted[i] = encrypted[i];
        }
    }

    decrypted[i] = '\0';

    printf("\n--- RESULT ---\n");
    printf("Plain Text  : %s", text);
    printf("Key         : %d\n", key);
    printf("Cipher Text : %s", encrypted);
    printf("Decrypted Text: %s", decrypted);

    return 0;
}
~~~
## OUTPUT:

<img width="1560" height="753" alt="image" src="https://github.com/user-attachments/assets/8ffbcf0d-2d40-4e69-9ee7-662adb0e879b" />



## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
