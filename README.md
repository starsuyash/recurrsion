# recurrsion
class Solution {
public:
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {
        vector<vector<int>> ans;
        vector<int> ds;
        findcombination(int ind, int target, vector<int>& candidates,
                        vector<int>& ds, vector<vector<int>>& ans);

        return ans;
    }
    void findcombination(int ind, int target, vector<int>& candidates,
                         vector<int>& ds, vector<vector<int>>& ans) {
        if (ind == n) {
            if (target == 0) {
                ans.push_back(ds);
            }
            return;
        }
        if (candidates[ind] <= target) {
            ds.push_back(candidates[ind]);
        }
        findcombination(ind, target - candidates[ind], candidates, ds, ans);
        ds.pop_back();
        findcombination(ind + 1, target, candidates, ds, ans);
    }
};
