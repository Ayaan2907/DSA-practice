https://leetcode.com/problems/remove-linked-list-elements/

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) {
//       if(head == NULL) return head;
//       ListNode* temp = head;
      
//       while(temp->next != NULL){
        
//         if(temp->val == val){
          
//           temp->next = temp->next->next;
          
//         }
//       }
//       return head;
      
        ListNode* temp;
        
        

        // Deleter all occurance of Key if it is present as head
        while(head != NULL && head->val == key){
            temp = head ->next;
            delete head;
            head = temp;
//         this loop is confusing
        }
        
        if(head == NULL) return head;
        
        ListNode* current = head->next;
        ListNode* previous = head;

        while(current != NULL){
            if(current->val == key){
                previous->next = current->next;
                delete current;
                current = previous->next;
                continue;
            }
            previous = current;
            current = current->next;
        }

        return head;
    }
};

```