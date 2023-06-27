# GFG Problem Of The Day

## Today - 27 June 2023
### Que - Union of Two Linked Lists

[Question Link](https://practice.geeksforgeeks.org/problems/union-of-two-linked-list/1)


### My approach
- Combine the heads of both list into a single list.
- Apply merge sort to sort the linked list.
- Eliminate duplicate elements from the sorted list.

---

### Code (c++) 
```cpp

class Solution
{
    public:
    Node* merge(Node* head1, Node* head2) {
        if (!head1)
            return head2;

        if (!head2)
            return head1;

        Node* smallerHead = NULL;

        if (head2->data > head1->data) {
            smallerHead = head1;
            smallerHead->next = merge(head1->next, head2);
        } else {
            smallerHead = head2;
            smallerHead->next = merge(head1, head2->next);
        }
        return smallerHead;
    }

    Node* mergeSort(Node* head) {
        if (!head || head->next == NULL)
            return head;

        Node* slow = head;
        Node* fast = head->next;

        while (fast != NULL && fast->next != NULL) {
            slow = slow->next;
            fast = fast->next->next;
        }

        Node* secondHalf = slow->next;
        slow->next = NULL;

        Node* sortedFirstHead = mergeSort(head);
        Node* sortedSecondHead = mergeSort(secondHalf);

        return merge(sortedFirstHead, sortedSecondHead);
    }

    Node* removeDuplicates(Node* head) {
        Node* curr = head;
        while (curr != NULL && curr->next != NULL) {
            if (curr->data == curr->next->data) {
                Node* temp = curr->next;
                curr->next = curr->next->next;
                delete temp;
            } else 
                curr = curr->next;
        }
        return head;
    }

    struct Node* makeUnion(Node* head1, Node* head2) {
        Node* mergedList = merge(head1, head2);
        Node* sortedList = mergeSort(mergedList);
        
        return removeDuplicates(sortedList);
    }
};
```

---

### Contribution

I always encourage contributors to participate in the discussion forum for this repository. If you have a better solution or any queries related to the `Problem of the Day` solution, please feel free to join the discussion. By sharing your insights and ideas, we can collectively enhance our coding knowledge and problem-solving skills.

To access the discussion section and engage in conversations, please [click here](https://github.com/getlost01/gfg-potd/discussions). I look forward to hearing from you and bring up  a collaborative learning environment.

---

#### If you find my solutions helpful, I would appreciate your support by considering giving a `⭐ star` to this repository.

---

#### Visitors
![GFG](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)