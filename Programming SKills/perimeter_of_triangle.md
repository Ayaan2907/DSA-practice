https://leetcode.com/problems/largest-perimeter-triangle/

```
class Solution {
public:
    int largestPerimeter(vector<int>& nums) {
      sort(nums.begin(), nums.end());
      
      for(int i= nums.size()-1; i>1;i--){
        int a = nums[i], b = nums[i-1], c= nums[i-2];
        
        if(a+b>c && b+c>a && a+c>b){
          return a+b+c;
        }else{
          continue;
        }
      }
      return 0;
    }
};
```