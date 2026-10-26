# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char text[100];
    int key[2][2] = {{3, 3}, {2, 5}};
    int i, a, b, c1, c2;

    printf("Enter the message: ");
    scanf("%s", text);

    for (i = 0; text[i] != '\0'; i++)
        text[i] = toupper(text[i]);

    int len = strlen(text);

    if (len % 2 != 0)
    {
        text[len] = 'X';
        text[len + 1] = '\0';
    }

    printf("Encrypted message: ");

    for (i = 0; text[i] != '\0'; i += 2)
    {
        a = text[i] - 'A';
        b = text[i + 1] - 'A';

        c1 = (key[0][0] * a + key[0][1] * b) % 26;
        c2 = (key[1][0] * a + key[1][1] * b) % 26;

        printf("%c%c", c1 + 'A', c2 + 'A');
    }

    printf("\n");

    return 0;
}
```
## OUTPUT
<img width="710" height="247" alt="Screenshot 2026-10-26 201815" src="https://github.com/user-attachments/assets/fd52811b-188e-46b6-b1bf-ad369f3c8017" />


## RESULT
**RESULT:**

Thus, the C program to implement the Hill Cipher substitution technique was executed successfully, and the given plaintext was encrypted into ciphertext using the key matrix.

