https://leetcode.com/problems/check-if-one-string-swap-can-make-strings-equal

was suggested to solve using hashing, but not needed
```
class Solution {
public:
  void swap(char &a, char &b){
    char temp = a;
    a =b;
    b = temp;
  }
    bool areAlmostEqual(string s1, string s2) {
      if(s1==s2) return true;
      
        for(int i=0; i<s2.size();i++){
          for(int j=i+1; j<s2.size();j++){
            swap(s2[i],s2[j]);
            if(s1==s2) return true;
            else swap(s2[i],s2[j]);
          }
        }
      return false;
    }
};
```