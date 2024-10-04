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
    ListNode* reverseKGroup(ListNode* head, int k) {
        // Count the number of nodes in the current group
        ListNode* node = head;
        int count = 0;
        while (node != NULL && count < k) {
            node = node->next;
            count++;
        }

        // If there are fewer than k nodes, return the head as is
        if (count < k) {
            return head;
        }

        // Reverse the k-group
        ListNode* next = NULL;
        ListNode* curr = head;
        ListNode* prev = NULL;
        int cnt = 0;

        while(curr != NULL && cnt < k) {
            next = curr->next;
            curr->next = prev;
            prev = curr;
            curr = next;
            cnt++;
        }

        // Recursively reverse the next groups and attach them
        if(next != NULL) {
            head->next = reverseKGroup(next, k);
        }

        // Return the new head of the reversed list
        return prev;
    }
};
