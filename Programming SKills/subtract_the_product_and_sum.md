https://leetcode.com/problems/subtract-the-product-and-sum-of-digits-of-an-integer/

```
class Solution {
public:
  void iterator(int &n, vector<int> &digits){
    while(n!=0){
      digits.push_back(n%10);
      n= n/10;
    }
    //generating an array of digits of input number, passing it by refrence
    return;
  }
    int subtractProductAndSum(int n) {
        vector<int> digits;
      iterator(n, digits);
      int sum = 0;
      long long int mult = 1;
      
      for(int i=0; i<digits.size();i++){
        sum+=digits[i];
        mult*=digits[i];
      }
      return (mult-sum);
    }
};
```