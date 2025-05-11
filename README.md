# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:

```
Name: K Hasini
Reg: 212224240074
```

```
#include <stdio.h>
#include <math.h>

long long power(long long base, long long exp, long long mod) {
    long long result = 1;
    while (exp > 0) {
        if (exp % 2 == 1) {
            result = (result * base) % mod;
        }
        base = (base * base) % mod;
        exp /= 2;
    }
    return result;
}

int main() {
    long long p, g, a, b, A, B, secretA, secretB;

    // Step 1: Publicly agreed values
    printf("Enter a large prime number (p): ");
    scanf("%lld", &p);

    printf("Enter a primitive root of %lld (g): ", p);
    scanf("%lld", &g);

    // Step 2: Private keys
    printf("\nEnter Private Key for User A: ");
    scanf("%lld", &a);

    printf("Enter Private Key for User B: ");
    scanf("%lld", &b);

    // Step 3: Calculate public keys
    A = power(g, a, p);
    B = power(g, b, p);

    printf("\nUser A's Public Key: %lld", A);
    printf("\nUser B's Public Key: %lld", B);

    // Step 4: Generate the Secret Key
    secretA = power(B, a, p);
    secretB = power(A, b, p);

    printf("\n\nShared Secret Key (computed by User A): %lld", secretA);
    printf("\nShared Secret Key (computed by User B): %lld\n", secretB);

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/8c0bd38e-006a-4a55-8b4d-c24349f48739)


## Result:
  The program is executed successfully

