# Project-
#include <stdio.h>


int AND(int a, int b);
int OR(int a, int b);
int NOT(int a);
int NAND(int a, int b);
int NOR(int a, int b);
int XOR(int a, int b);


int binary_input() 
{
    int c;
   while(1)
   {
        scanf("%d", &c);
        if (c == 0 || c == 1) {
           return c;
        } else {
            printf("Invalid input! Please enter 0 or 1.\n");
        }
        }
}

int main() {
    int choice, a, b, result;

    while (1) {
        printf("\n--- Logic Gate Simulator ---\n");
        printf("1. AND Gate\n");
        printf("2. OR Gate\n");
        printf("3. NOT Gate\n");
        printf("4. NAND Gate\n");
        printf("5. NOR Gate\n");
        printf("6. XOR Gate\n");
        printf("7. Exit\n");
        printf("Choose a gate (1-6) or exit (7): ");
        scanf("%d", &choice);

        if (choice == 7) {
            printf("Exiting...\n");
            break;
        }

        switch (choice) {
            case 1: 
            case 2:
            case 4: 
            case 5:
            case 6: 
                printf("Enter two binary inputs (0 or 1): ");
                a = binary_input();
                b =binary_input();
                break;

            case 3: 
                printf("Enter a binary input (0 or 1): ");
                a = binary_input();
                break;

            default:
                printf("Invalid choice! Please select a valid option.\n");
                continue;
        }

        
        switch (choice) {
            case 1:
                result = AND(a, b);
                printf("AND(%d, %d) = %d\n", a, b, result);
                break;
            case 2: 
                result = OR(a, b);
                printf("OR(%d, %d) = %d\n", a, b, result);
                break;
            case 3: 
                result = NOT(a);
                printf("NOT(%d) = %d\n", a, result);
                break;
            case 4: 
                result = NAND(a, b);
                printf("NAND(%d, %d) = %d\n", a, b, result);
                break;
            case 5:
                result = NOR(a, b);
                printf("NOR(%d, %d) = %d\n", a, b, result);
                break;
            case 6:
                result = XOR(a, b);
                printf("XOR(%d, %d) = %d\n", a, b, result);
                break;
        }
    }

    return 0;
}


int AND(int a, int b) {
    return a & b;
}

int OR(int a, int b) {
    return a | b;
}

int NOT(int a) {
    return !a;
}

int NAND(int a, int b) {
    return !(a & b);
}

int NOR(int a, int b) {
    return !(a | b);
}

int XOR(int a, int b) {
    return a ^ b;
}
