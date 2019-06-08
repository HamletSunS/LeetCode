## 171Excel表列序号
```cpp
class Solution {
public:
    int titleToNumber(string s) {
        string sr=reverse(s);
        int ret=0;
        int n=sr.size();
        for(int i=0;i<n;++i){
            int digit=s[i]-'A'+1;
            ret*=26;
            ret+=digit;
        }
        return ret;
    }
    
private:
    string reverse(string s){
        int n=s.size();
        if(n<2)
            return s;
        for(int i=0;i<n/2;++i){
            swap(s[i],s[n-1-i]);
        }
        return s;
    }
};
```
思路：
1. 反转字符串+进制转换
2. 26进制转换注意一下这里是从1--26，而不是0--25 

拓展：  
如何根据把列号（数字）转换成字母 1->A 2->B .. 26->Z 27->AA 28->AB