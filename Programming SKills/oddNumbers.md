https://leetcode.com/problems/count-odd-numbers-in-an-interval-range/submissions/

```
class Solution {
public:
    bool isOdd(int num){
        if(num%2==0) return false;
        
        return true;        
    }
    bool isEven(int num){
        if(num%2==0) return true;
        
        return false;        
    }
    
    int countOdds(int low, int high) {
        int ans =0;
        int difference = (high - low );
        if(isEven(high) && isEven(low))ans = (difference/2);
        if(isOdd(high) && isOdd(low)) ans = (difference/2)+1;
        if(isEven(high)&&isOdd(low) || isOdd(high)&&isEven(low))
            ans = 1+(difference/2);
        
        return ans;
        
        
        
        
        
        
        
        
        
        
        
        
        /////////////////////// first approach below
//         int difference = high - low + 1;
        
//         int ans = 0;
//         bool flag = false;  //holding the check for the inputs odd or even
        
//         if(high%2!=0){
//             ans++;
//             flag = true;
//         }
//         if(low%2!=0){
//             ans++;            
//             flag = true;
//         }
        
//         if(difference>1) {
//             ans+= difference/2;
//         }
//         if(flag)
//             ans-=1;  // if one of the input is odd the count has to be reduced by 1.
//         return ans;
        
// // first check  high and low : odd?even  increase count if odd
// // odd- odd = odd, and diffenece/ 2 to get odds and skip evens, so here high will be            calculaeted again. thrfr difference/2 -1 = ans
// // odd-even or even - odd = odd. thrfr oddCount = floor(diffference/2) 
// // even-even = even, ans = diff/2
            
    }
};
```
