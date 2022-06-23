

```
class Solution {
public:
    double average(vector<int>& salary) {

        long long int sum =0;
        int minSlry = INT_MAX;
        int maxSlry = INT_MIN;
        int n = salary.size();
        
        for(int i=0; i<n; i++){
            minSlry = (salary[i]<minSlry)?(salary[i]):(minSlry);
            maxSlry = (salary[i]>maxSlry)?(salary[i]):(maxSlry);
            sum = sum+salary[i];
        }
        
        sum = sum - minSlry;
        sum = sum - maxSlry;
        // double avg = (sum/(n-2)); //earlier it was not tyecasted. so getting wrong answer

        // return avg;
       return (sum/(salary.size()-2.0)); //earlier it was -2, so ans was 41.000 but correct ans was 41.111, it was bcz while -2 its an int, to make it float or double we have to use 2.0 or double(2)

        
        
    }
};
```

# key learning
1. when told to return value with precision, follow that.
2. in this problem i was doing all right, initialised with double but in last operation while returning the average, we have to decrease the size by 2
 there i was performing operation in int. to make it float 2.0 is needed
 > a rough description