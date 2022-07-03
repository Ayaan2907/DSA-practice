https://leetcode.com/problems/find-nearest-point-that-has-the-same-x-or-y-coordinate/

```
class Solution {
public:
    int nearestValidPoint(int x, int y, vector<vector<int>>& p) {
//       int ans = INT_MAX, index=0;
//       for(int i=0; i<points.size();i++){
//         if(points[i][0]==x || points[i][1]==y){
//           int temp = ans;
//           int newDistance = abs(x-points[i][0])+abs(y-points[i][1]));
//           ans= min(ans, newDistance) 
//           if(temp == ans)index++;
//           if(i==points.size()-1)return index;
//         }
//       }
//       return -1;
    
//         at this point solution not working, jumbled in problem statement, first i was returning index of smallest one, but smallest distance can b with multiple co-ordinates, so now counting the smallest, and got jumbled,
        // now looking at the soln
        
        // sprry i have to return the first index of minimum distance values 
      
//       //////////////////////////
      
//       int minDis= INT_MAX;
      
//       for(int i=0; i<A.size();i++){
//        if(A[i][0]==x || A[i][1]==y){
//           int dist = abs(A[i][0]-x)+abs(A[i][1]-y); 
//          minDis = min(minDis, dist);
//        }
//       }
      
//       if(minDis ==INT_MAX)return -1;
      
//       for(int i=0;i<A.size();i++){
//          if(A[i][0]==x || A[i][1]==y && minDis == (abs(A[i][0]-x)+abs(A[i][1]-y))){
//            return i;
//       }
//       }
//     return -1;




    int mind=INT_MAX;
		for(int i=0;i<p.size();i++){
			if(p[i][0]==x || p[i][1]==y){
				int d=abs(x-p[i][0])+abs(y-p[i][1]);
				mind=min(d,mind);
			}
		}
		if(mind==INT_MAX)return -1;
		for(int i=0;i<p.size();i++){
			if((p[i][0]==x || p[i][1]==y) && mind==abs(x-p[i][0])+abs(y-p[i][1])){
				return i;
			}
		}
		return -1;
    }
};
```