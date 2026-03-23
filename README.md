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
#include <stdio.h>
long long int power(long long int base, long long int exp, long long int mod)
{
    long long int result = 1;
    base = base % mod;
    while (exp > 0)
    {
        if (exp % 2 == 1)
            result = (result * base) % mod;
        exp = exp >> 1;
        base = (base * base) % mod;
    }
    return result;
}
int main()
{
    long long int P, G, a, b, x, y, ka, kb;
    printf("Enter the value of P (prime number): ");
    scanf("%lld", &P);
    printf("Enter the value of G (primitive root of P): ");
    scanf("%lld", &G);
    printf("Enter private key a for VISHAL: ");
    scanf("%lld", &a);
    printf("Enter private key b for RAJESH: ");
    scanf("%lld", &b);
    x = power(G, a, P);
    y = power(G, b, P);
    ka = power(y, a, P);
    kb = power(x, b, P);
    printf("\nPublic key of VISHAL: %lld", x);
    printf("\nPublic key of RAJESH: %lld", y);
    printf("\n\nSecret key for VISHAL: %lld", ka);
    printf("\nSecret key for RAJESH: %lld", kb);
}
```



## Output:
<img width="1415" height="779" alt="image" src="https://github.com/user-attachments/assets/0077a611-91b5-4a06-b388-00ca3b814775" />



## Result:
  The program is executed successfully

