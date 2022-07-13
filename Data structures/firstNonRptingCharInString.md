https://leetcode.com/problems/first-unique-character-in-a-string/
```
class Solution {
public:
    int firstUniqChar(string s) {

      vector<int> alpha(26,0);
//     s[i]-'a' is to get the integer index of that char using ASCII
//       we are increasing the count of that letter, and finally checking count of that letter
      for(int i=0; i<s.size(); i++) alpha[s[i]-'a']++;  
      
      for(int i=0; i<s.size(); i++) if(alpha[s[i]-'a']==1) return i;
      
      return -1;
       
    }
};
```