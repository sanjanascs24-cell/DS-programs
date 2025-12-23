#include <stdio.h>
#include <stdlib.h>

/* Node structure */
struct Node {
    int data;
    struct Node* next;
};

/* Heads of two linked lists */
struct Node* head1 = NULL;
struct Node* head2 = NULL;

/* Insert at end */
struct Node* insertEnd(struct Node* head) {
    int val;
    struct Node *newNode, *temp;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    printf("Enter data: ");
    scanf("%d", &val);

    newNode->data = val;
    newNode->next = NULL;

    if (head == NULL)
        return newNode;

    temp = head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    return head;
}

/* Display list */
void display(struct Node* head) {
    if (head == NULL) {
        printf("List is empty\n");
        return;
    }

    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

/* Sort linked list (Bubble Sort) */
void sortList(struct Node* head) {
    int temp;
    struct Node *i, *j;

    if (head == NULL) return;

    for (i = head; i->next != NULL; i = i->next) {
        for (j = i->next; j != NULL; j = j->next) {
            if (i->data > j->data) {
                temp = i->data;
                i->data = j->data;
                j->data = temp;
            }
        }
    }
    printf("List sorted successfully\n");
}

/* Reverse linked list */
struct Node* reverseList(struct Node* head) {
    struct Node *prev = NULL, *curr = head, *next = NULL;

    while (curr != NULL) {
        next = curr->next;
        curr->next = prev;
        prev = curr;
        curr = next;
    }
    printf("List reversed successfully\n");
    return prev;
}

/* Concatenate two lists */
struct Node* concatenate(struct Node* h1, struct Node* h2) {
    struct Node* temp;

    if (h1 == NULL) return h2;

    temp = h1;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = h2;
    printf("Lists concatenated successfully\n");
    return h1;
}

/* Main function */
int main() {
    int choice;

    while (1) {
        printf("\n--- Singly Linked List Menu ---\n");
        printf("1. Insert into List 1\n");
        printf("2. Insert into List 2\n");
        printf("3. Display List 1\n");
        printf("4. Display List 2\n");
        printf("5. Sort List 1\n");
        printf("6. Reverse List 1\n");
        printf("7. Concatenate List1 and List2\n");
        printf("8. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
        case 1:
            head1 = insertEnd(head1);
            break;
        case 2:
            head2 = insertEnd(head2);
            break;
        case 3:
            display(head1);
            break;
        case 4:
            display(head2);
            break;
        case 5:
            sortList(head1);
            break;
        case 6:
            head1 = reverseList(head1);
            break;
        case 7:
            head1 = concatenate(head1, head2);
            head2 = NULL;
            break;
        case 8:
            return 0;
        default:
            printf("Invalid choice\n");
        }
    }
}
