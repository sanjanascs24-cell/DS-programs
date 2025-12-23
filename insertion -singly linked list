#include <stdio.h>
#include <stdlib.h>

/* Node structure */
struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

/* Insert at beginning */
void insertAtBeginning() {
    int val;
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));

    printf("Enter data: ");
    scanf("%d", &val);

    newNode->data = val;
    newNode->next = head;
    head = newNode;
}

/* Insert at end */
void insertAtEnd() {
    int val;
    struct Node *newNode, *temp;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    printf("Enter data: ");
    scanf("%d", &val);

    newNode->data = val;
    newNode->next = NULL;

    if (head == NULL) {
        head = newNode;
        return;
    }

    temp = head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
}

/* Insert at any position */
void insertAtPosition() {
    int pos, val, i;
    struct Node *newNode, *temp;

    printf("Enter position: ");
    scanf("%d", &pos);
    printf("Enter data: ");
    scanf("%d", &val);

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;

    if (pos == 1) {
        newNode->next = head;
        head = newNode;
        return;
    }

    temp = head;
    for (i = 1; i < pos - 1 && temp != NULL; i++)
        temp = temp->next;

    if (temp == NULL) {
        printf("Invalid position\n");
        free(newNode);
        return;
    }

    newNode->next = temp->next;
    temp->next = newNode;
}

/* Display linked list */
void display() {
    struct Node* temp = head;

    if (temp == NULL) {
        printf("List is empty\n");
        return;
    }

    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    int choice;

    while (1) {
        printf("\n--- Singly Linked List Menu ---\n");
        printf("1. Insert at Beginning\n");
        printf("2. Insert at End\n");
        printf("3. Insert at Position\n");
        printf("4. Display\n");
        printf("5. Exit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
        case 1:
            insertAtBeginning();
            break;
        case 2:
            insertAtEnd();
            break;
        case 3:
            insertAtPosition();
            break;
        case 4:
            display();
            break;
        case 5:
            return 0;
        default:
            printf("Invalid choice\n");
        }
    }
}
