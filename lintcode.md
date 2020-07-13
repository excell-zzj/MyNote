~~~c++
class Solution {
public:
    /**
     * @param arr: string array
     * @param query: query array
     * @return: return  LCP ans array
     */
    int search(string a, string b){
        int i = 0;
        while(a[i]!=NULL && b[i] !=NULL && a[i] == b[i]){
            ++i;
        }
        return i;
    }
    int minSearch(vector<int> pre, int start, int end){
        int res = pre[start];
        for(int i = start+1; i <end; ++i){
            res = min(res, pre[i]);
        }
        return res;
    }
    vector<int> queryLCP(vector<string> &arr, vector<vector<int>> &query) {
        // write your code here
        int n = arr.size();
        vector<int> pre;
        vector<int> ans;
        for(int i = 0; i < n-1; ++i){
            int res = search(arr[i], arr[i+1]);
            pre.push_back(res);
        }
        int m = query.size();
        for(int i = 0; i < m; ++i){
            int first = query[i][0];
            int second = query[i][1];
            int res = minSearch(pre, first, second-1);
            ans.push_back(res);
        }
        return pre;
    }
};
~~~

