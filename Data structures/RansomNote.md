https://leetcode.com/problems/ransom-note/

```
class Solution {
public:
    bool canConstruct(string ransomNote, string magzine) {
//         if(ransomNote.size()> magzine.size()) return false;
        
//       for(int i=0; i<magzine.size();i++){
        
//       if(ransomNote[0]==magzine[i]){
//         for(int j=1; j<ransomNote.size();j++){
//           if(ransomNote[j]!=magzine[i+j])
//             break;
//         }
          
//         }
//       }

      <!  ap2   --  -->
      sort(ransomNote.begin(), ransomNote.end());
      sort(magzine.begin(), magzine.end());
      int res = 0;
      
      for(auto itr: magzine){
        if(itr==ransomNote[res]) res++;
      }
      return res>=ransomNote.length()? true:false;
    }
};

// check if magzine contains ransomNote
// if sizes of note is greater false
// if char 0 is equal the check for next char 


// ap2
// sort and match the chars
```
pointing to magzine elements using itr pointer, checking that pointer with the index of ransomNote, and increasing response if its greater the size of ransomNote then true else false 

study iterators and aut https://www.geeksforgeeks.org/iterators-c-stl/