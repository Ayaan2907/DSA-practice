https://leetcode.com/problems/two-sum/

```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
      vector<int> ans;
      unordered_map<int, int> indices;
      
      for(int i=0; i<nums.size(); i++){
        int diff = target - nums[i];
        if(indices.find(diff) != indices.end()){
          ans.push_back(i);
          ans.push_back(indices[diff]);
        }else{
          // indices.insert(&i, nums[i]);
          indices[nums[i]]=i;
        }   
      }
  return ans;
    }
};


// steps
// dif = target-nums[i]
// if(HashMap.find(dif)
//    ans.push i, ans.push hashMap.index
// else
  // hashMap.insert(dif)
// return ans
```

work on syntax of HashMap
alhamdulillah came up with exact soln at first go and had a correct soln. 