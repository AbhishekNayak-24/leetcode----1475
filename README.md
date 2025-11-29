# leetcode----1475
Final Prices with a special discount in a shop
//code in C++
class Solution {
 public:
  vector<int> finalPrices(vector<int>& prices) {
    vector<int> ans{prices};
    stack<int> stack;

    for (int j = 0; j < prices.size(); ++j) {
      // stack[-1] : = i in the problem description.
      while (!stack.empty() && prices[j] <= prices[stack.top()])
        ans[stack.top()] -= prices[j], stack.pop();
      stack.push(j);
    }

    return ans;
  }
};
