#include <iostream>
#include <vector>
using namespace std;

int main()
{
    int n, W;

    // 1. Start
    // 2. Read number of items, weights, profits and capacity
    cout << "Enter number of items: ";
    cin >> n;

    vector<int> weight(n + 1);
    vector<int> profit(n + 1);

    cout << "Enter weights:\n";
    for (int i = 1; i <= n; i++)
        cin >> weight[i];

    cout << "Enter profits:\n";
    for (int i = 1; i <= n; i++)
        cin >> profit[i];

    cout << "Enter knapsack capacity: ";
    cin >> W;

    // 3. Create DP table
    vector<vector<int>> dp(n + 1, vector<int>(W + 1, 0));

    // 4. For each item and each capacity
    for (int i = 1; i <= n; i++)
    {
        for (int w = 1; w <= W; w++)
        {
            // If item fits
            if (weight[i] <= w)
            {
                // Choose maximum:
                // a) Don't take
                // b) Take
                dp[i][w] = max(
                    dp[i - 1][w],
                    profit[i] + dp[i - 1][w - weight[i]]
                );
            }
            else
            {
                // Don't take the item
                dp[i][w] = dp[i - 1][w];
            }
        }
    }

    // 5. Last value = maximum profit
    cout << "\nMaximum Profit = " << dp[n][W] << endl;

    // 6. Stop
    return 0;
}
