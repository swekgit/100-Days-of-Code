#include <stdio.h>
#include <stdlib.h>
#include <unordered_map>
#include <vector>

using namespace std;

int main() {
    int n;
    scanf("%d", &n);
    
    int A[n+1];
    for (int i = 1; i <= n; i++) {
        scanf("%d", &A[i]);
    }
    
    // Step 1: Calculate the prefix sum array.
    long long prefix[n+1];
    prefix[0] = 0;
    for (int i = 1; i <= n; i++) {
        prefix[i] = prefix[i-1] + A[i];
    }

    // Step 2: Use a hashmap to store subarray sums.
    unordered_map<long long, vector<pair<int, int>>> sum_map;
    
    // Step 3: Record all subarrays' sums and their indices
    for (int L = 1; L <= n; L++) {
        for (int R = L; R <= n; R++) {
            long long subarray_sum = prefix[R] - prefix[L-1];
            sum_map[subarray_sum].push_back({L, R});
        }
    }

    // Step 4: Count valid pairs of non-overlapping subarrays with the same sum
    int count = 0;

    // For each sum in the map
    for (auto& entry : sum_map) {
        vector<pair<int, int>>& intervals = entry.second;

        // Check pairs of subarrays
        for (int i = 0; i < intervals.size(); i++) {
            for (int j = i + 1; j < intervals.size(); j++) {
                int L1 = intervals[i].first;
                int R1 = intervals[i].second;
                int L2 = intervals[j].first;
                int R2 = intervals[j].second;
                
                // Ensure subarrays do not overlap
                if (R1 < L2 || R2 < L1) {
                    count++;
                }
            }
        }
    }
    
    // Output the result
    printf("%d\n", count);

    return 0;
}
