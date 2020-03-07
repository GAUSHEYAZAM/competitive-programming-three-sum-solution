# competitive-programming-three-sum-solution
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        
        vector<vector<int>> arr;
        sort(nums.begin(), nums.end());
        int n=nums.size();
        for(int i=0;i<n-1; i++){
            if (i > 0 && nums[i] == nums[i - 1]){
                continue;
            }
            int s=i+1;
            int e=n-1;
            int x=nums[i];
            while(s<e){
                if(s>i+1 && nums[s]==nums[s-1]) {
                    s++;
                    continue;
                }
                if(e<n-1 && nums[e]==nums[e+1]){
                    e--;
                    continue;
                }
                
                if(x+nums[s]+nums[e]==0){
                   arr.push_back({x,nums[s], nums[e]});
                    s++;
                    e--;
                }else if(x+nums[s]+nums[e]>0){
                    e--;
                }else{
                    s++;
                }
            }
            
        }
        return arr;
    }
};
