https://leetcode.com/problems/reshape-the-matrix/

```
class Solution {
public:
    vector<vector<int>> matrixReshape(vector<vector<int>>& mat, int r, int c) {
      int m= mat.size(); 
      int n= mat[0].size();
      vector<int> one_d;
      
      // if(r==m && c ==n) return mat;
//       c=c/r;
      if(c*r != m*n) return mat; //checking for dimensions 
      for(int i=0; i<m; i++){
        for(int j=0; j<n;j++){
          one_d.push_back(mat[i][j]);
        }
      }

      vector<vector<int>> ans(r, vector<int>(c,0));
      int itr =0;
      for(int i=0; i<r;i++){
        for(int j=0; j<c; j++){
          ans[i][j]=one_d[itr];
          itr++;
        }
      }
      return ans;
    }
};

```
1. if dimensions are same return same matrix
2. iterate matrix and store all elemnts in one dimensional vector
3. iterate one dimensional vector and store elements in 2d vector
4. return 2d vector
