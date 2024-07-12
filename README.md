class Solution{
public:
    int isStackPermutation(int N,vector<int> &A,vector<int> &B){
        stack<int> st;
        int i=0,j=0;
        while(j<N)
        {
            while(i<N && (st.empty() || st.top()!=B[j]))
            {
                st.push(A[i]);
                i++;
            }
            while(!st.empty() && st.top()==B[j])
            {
                st.pop();
                j++;
            }
            if(i==N && !st.empty() && st.top()!=B[j])
            return 0;
        }
        return 1;
    }
};
