#### Name : Sowmya V
#### Reg no : 212222110045
#### Date : 

## EX - 14 : Hash Function

### Aim:
To implement a simple hash function in C to convert a string into a fixed-size hash value using basic hashing techniques.

### Algorithm
Step 1:
Initialize a hash value (e.g., to 0 or a large prime number).

Step 2:
For each character in the input string , Multiply the current hash value by a constant (e.g., a prime number).

Step 3:
Add the ASCII value of the character to the hash and apply a modulo operation to keep the hash value within bounds if necessary.

Step 4:
Return the computed hash value.

Step 5:
Test the hash function with different strings to observe how the output varies.

### Program:
```
#include <stdio.h>
#include <string.h>

unsigned long hashFunction(const char *str)
{
    unsigned long hash = 5381;  
    int c;
    
    while ((c = *str++))
    {
        hash = ((hash << 5) + hash) + c;
    }
    
    return hash;
}

int main()
{
    char input[256];
    printf("Enter the string to hash: ");
    fgets(input, sizeof(input), stdin);
    input[strcspn(input, "\n")] = 0;  
    unsigned long hashValue = hashFunction(input);
    printf("Hash value of '%s' is: %lu\n", input, hashValue);
    return 0;
}

```
### Output

![image](https://github.com/user-attachments/assets/48e95429-12f0-4861-86aa-92284cbb0795)

### Result
Implementation of Hash function was successful.
