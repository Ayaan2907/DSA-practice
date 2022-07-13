https://leetcode.com/problems/pascals-triangle/


```
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> ans;
      for(int i=1; i<=numRows;i++){
        vector<int> row(i);
        row[0]=1;
        row[i-1]=1;
        ans.push_back(row);
      }
      
      for(int i=2; i<numRows; i++){
        for(int j=1; j<i; j++){ 
          ans[i][j]=(ans[i-1][j-1] + ans[i-1][j]);
        }
      }
      return ans;
    }
};

// declare matrix with numRows
// push_back vectors of i size as size of each row with all 1s
// iterate as i from index 2 to < numRows
//       then iterate as j in each row from 1 to <i
//    newMatrix[i][j]=(newMatrix[i-1][j-1] + newMatrix[i-1][j])

// return newMatrix

```

find a recursive solution check if exist or not

we can do it in one iteration also
