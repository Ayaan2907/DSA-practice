https://leetcode.com/problems/contains-duplicate/

```
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
     unordered_set<int> present;
      for(int i=0; i<nums.size(); i++){
        if (present.find(nums[i]) == present.end()) present.insert(nums[i]);
        else return true;
      }
      return false;
    }
};

// can also be done by XOR operations read on it 
```