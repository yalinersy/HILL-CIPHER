# HILL CIPHER

## EX. NO: 3 IMPLEMENTATION OF HILL CIPHER
## AIM:
   
To write a C program to implement the hill cipher substitution techniques.

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

int main() {
    int key[3][3] = {
        {6, 24, 1},
        {13, 16, 10},
        {20, 17, 15}
    };

    char text[] = "MEETME";
    int i, j, k;
    int pt[3], ct[3];

    printf("Key Matrix:\n");
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 3; j++) {
            printf("%d ", key[i][j]);
        }
        printf("\n");
    }

    printf("\nPlain Text: %s\n", text);

    for (i = 0; i < 6; i += 3) {

        for (j = 0; j < 3; j++) {
            pt[j] = text[i + j] - 'A';
        }

        for (j = 0; j < 3; j++) {
            ct[j] = 0;
            for (k = 0; k < 3; k++) {
                ct[j] += key[j][k] * pt[k];
            }
            ct[j] = ct[j] % 26;
        }

        for (j = 0; j < 3; j++) {
            text[i + j] = ct[j] + 'A';
        }
    }

    printf("Cipher Text: %s\n", text);

    return 0;
}

```
## OUTPUT

<img width="409" height="255" alt="image" src="https://github.com/user-attachments/assets/4f97b3e2-b1fa-4f21-90cd-65a770815ac7" />

## RESULT

Thus, a C program to implement the hill cipher substitution techniques is succuessfully implmented.
