https://leetcode.com/problems/linked-list-cycle/

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode *head) {
      ListNode *slow = head;
      ListNode *fast = head;
      
      if(head == NULL) return false;
      while(fast != NULL && fast->next != NULL){

        fast = fast->next->next;
        slow = slow->next;  
        if(fast == slow) return true;
      }
      return false;
    }
};


// ap-2 
// 2 pointers, slow, fast, iterate if slow==fast means its having a cycle

// AP-1 misunderstood the question

// check if head null return false;
// iterate till lastNode NULL
// check next addr in HashSet if present return true else add it to hashSet, temp=temp->next
// return false in final


//    bool hasCycle(ListNode *head) {
//       unordered_set<ListNode*>HS;
//       ListNode *temp = head;

//       while(temp->next!=NULL){
//         ListNode *address = temp->next;
//         const bool is_in = HS.find(address) != HS.end();
//         if(is_in) return true;
//         HS.insert(address);
//         temp=address;
//       }
//       return false;
//     }

```