https://leetcode.com/problems/intersection-of-two-arrays-ii/

```

// chech for array with smaller size()
// nexted loopthroug it and check for similar elements
// pushback to ans.

class Solution {
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
      int m  = nums1.size();
      int n = nums2.size();
      vector<int> ans;
      
      for(int i=0; i<n; i++){
        
        for(int j=0; j<m; j++){
          
          if(nums2[i]==nums1[j] ){
            ans.push_back(nums1[j]);
            nums1[j] = INT_MAX;
            nums2[i]=INT_MIN;
          }
          
        }
        
      }
      return ans;
    }
};


// another approach using hashMap, iterate array 1 insert into hashMap
// iterate array 2 check present or not, match the number of times its coming in both arrays
// push to answer and return ans


```
