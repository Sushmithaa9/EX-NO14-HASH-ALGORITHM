# EX-NO14-HASH-ALGORITHM

## AIM:
To implement HASH ALGORITHM

## ALGORITHM:

1. Hash Algorithm is used to convert input data (message) into a fixed-size string, typically a hash value, which uniquely represents the original data.

2. Initialization:
   - Choose a hash function \( H \) (e.g., SHA-256, MD5, etc.).
   - The message \( M \) to be hashed is input.

3. Message Preprocessing:
   - Break the message \( M \) into fixed-size blocks. If necessary, pad the message to make it compatible with the block size required by the hash function.
   - For example, in SHA-256, the message is padded to ensure that its length is a multiple of 512 bits.

4. Hash Calculation:
   - Process the message block by block, applying the hash function \( H \) iteratively to produce an intermediate hash value.
   - For SHA-256, each block is processed through a series of logical operations, bitwise manipulations, and modular additions.

5. Output:
   - After all blocks are processed, the final hash value (digest) is produced, which is a fixed-size output (e.g., 256-bit for SHA-256).
   - The resulting hash is unique to the input message, meaning even a small change in the message will result in a completely different hash.

6. Security: The strength of the hash algorithm lies in its collision resistance, ensuring that it is computationally infeasible to find two different messages that produce the same hash value.


## Program:

#include <stdio.h>
#include <string.h>
unsigned long hashFunction(char str[])
{
    unsigned long hash = 5381;
    int i;
    for (i = 0; str[i] != '\0'; i++)
        hash = ((hash << 5) + hash) + str[i];
    return hash;
}
int main()
{
}
    char message[200];
    unsigned long hash;
    printf("Enter the message: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = '\0';
    hash = hashFunction(message);
    printf("\nHash Value: %lu\n", hash);
    return 0;
## Output:
<img width="902" height="373" alt="image" src="https://github.com/user-attachments/assets/7361c797-6e0b-4a5c-966d-4167e9611dc2" />


## Result:
The program is executed successfully.
