#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_PRODUCTS 100

struct Product {
    char name[50];
    int quantity;
    float price;
};

struct Product products[MAX_PRODUCTS];
int numProducts = 0;

void addProduct() {
    if (numProducts < MAX_PRODUCTS) {
        printf("Enter product name: ");
        scanf("%s", products[numProducts].name);
        printf("Enter quantity: ");
        scanf("%d", &products[numProducts].quantity);
        printf("Enter price: ");
        scanf("%f", &products[numProducts].price);
        numProducts++;
    } else {
        printf("No more space for new products!\n");
    }
}

void displayProducts() {
    printf("Products available:\n");
    printf("Name\tQuantity\tPrice\n");
    for (int i = 0; i < numProducts; i++) {
        printf("%s\t%d\t\t%.2f\n", products[i].name, products[i].quantity, products[i].price);
    }
}

int main() {
    int choice;
    do {
        printf("\nPharmacy Store Management System\n");
        printf("1. Add Product\n");
        printf("2. Display Products\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                addProduct();
                break;
            case 2:
                displayProducts();
                break;
            case 3:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice!\n");
        }
    } while (choice != 3);

    return 0;
}
