https://leetcode.com/problems/happy-number/solution/

problem was based on hashSet
faced many errors while solving


```
/*
class Solution {
public:
  //getting a TLE but whyyyyyy
  // vector< int> past; //storing the numbers whose square sum is other than 1  
  unordered_set<int> pastNumbersHashSet ={1};
    bool isHappy(int num) {
      //vector<int> past(1); err: runtime err: running a function recursively, but u forgot that initializing this inside fn will overwrite it every time. make it global 
      long long int nextNumber=0;
      if(num ==1) return true;
      
      if(pastNumbersHashSet.find(num) != pastNumbersHashSet.end()) return false;
      // for(int i=0; i<past.size();i++){
        // if(num==past[i]) return false;
      // }
      
      while(num!=0){
        int digit = num%10;
        nextNumber+= (digit*digit);
        num/=10;
      }
      // past.push_back(num);
      pastNumbersHashSet.insert(num);
      return(isHappy(nextNumber));
    }
};


//  used a vector<int> past to store the past numbers, and in every function call was looping through it and checking the presence ==> o(n) time just for checking

// use a hashSet, it takes only O(1) time to check
*/


// not sure whyyyyy is it not working
class Solution {
public:
    int sumDigits(int num){
        int sum{0};
        while(num != 0){
            sum += (num % 10) * (num % 10);
            num /= 10;
        }
        return sum;
    }
    bool isHappy(int n) {
        bool ans = false;
        vector<int> track;
        for(int l{1}; l > 0; l++){
            int sumOfNum = sumDigits(n);
            if(sumOfNum == 1){
                ans = true;
                break;
            }else{
                track.push_back(n);
                n = sumOfNum;
            }
            int t{0};
            for(int i{0}; i < track.size() - 1; i++){
                if(track[i] == n){
                    ans = false;
                    t++;
                    break;
                }
            }
            if(t != 0)
                break;
        }
        return ans;
    }
};

```