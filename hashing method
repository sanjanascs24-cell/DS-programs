#include <stdio.h>

#define SIZE 10

int hashTable[SIZE];

// Initialize hash table
void init() {
    for (int i = 0; i < SIZE; i++) {
        hashTable[i] = -1;
    }
}

// Hash function
int hashFunction(int key) {
    return key % SIZE;
}

// Insert key into hash table
void insert(int key) {
    int index = hashFunction(key);

    // Linear probing
    while (hashTable[index] != -1) {
        index = (index + 1) % SIZE;
    }

    hashTable[index] = key;
    printf("Inserted %d at index %d\n", key, index);
}

// Search key in hash table
void search(int key) {
    int index = hashFunction(key);
    int startIndex = index;

    while (hashTable[index] != -1) {
        if (hashTable[index] == key) {
            printf("Key %d found at index %d\n", key, index);
            return;
        }
        index = (index + 1) % SIZE;

        if (index == startIndex)
            break;
    }

    printf("Key %d not found\n", key);
}

// Display hash table
void display() {
    printf("\nHash Table:\n");
    for (int i = 0; i < SIZE; i++) {
        if (hashTable[i] == -1)
            printf("%d : Empty\n", i);
        else
            printf("%d : %d\n", i, hashTable[i]);
    }
}

int main() {
    int choice, key;
    init();

    while (1) {
        printf("\n1. Insert\n2. Search\n3. Display\n4. Exit\n");
        printf("Enter choice: ");
        scanf("%d", &choice);

        switch (choice) {
        case 1:
            printf("Enter key: ");
            scanf("%d", &key);
            insert(key);
            break;
        case 2:
            printf("Enter key to search: ");
            scanf("%d", &key);
            search(key);
            break;
        case 3:
            display();
            break;
        case 4:
            return 0;
        default:
            printf("Invalid choice\n");
        }
    }
}
