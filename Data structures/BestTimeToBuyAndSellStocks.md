https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

```
class Solution {
public:
    int maxProfit(vector<int>& prices) {
      int buy = INT_MAX;
      // int sell = INT_MIN;
      int n= prices.size();
      // int buyIndex = 0; notnneeded in app2
      int finalProfit =0;
      int profitOfTheDay =0;

      for(int i=0; i<n; i++){
        if(prices[i]<buy){
          buy=prices[i];
          // buyIndex=i;        
        } 
        
      // }

//       for(int i= buyIndex+1; i<prices.size(); i++){
//         if(prices[i]>sell) sell=prices[i];        
//       } instead of calculating based on 
      
     profitOfTheDay = prices[i] - buy;
        if(finalProfit<profitOfTheDay){
          finalProfit = profitOfTheDay;
        }
      }
      // return (profit>0)? profit:0;
        return finalProfit;
    }
};
```