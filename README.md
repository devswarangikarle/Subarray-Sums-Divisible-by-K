# Subarray-Sums-Divisible-by-K

Given an integer array nums and an integer k, return the number of non-empty subarrays that have a sum divisible by k.
A subarray is a contiguous part of an array.

Constraints:
1 <= nums.length <= 3 * 10^4
-10^4 <= nums[i] <= 10^4
2 <= k <= 10^4

class Solution:
    def subarraysDivByK(self, nums: List[int], k: int) -> int:
        mods  = [0] * k
        m     = 0
        count = 0
        mods[0] = 1

        for num in nums:
            m = (m + num) % k 
            count += mods[m]
            mods[m] += 1

        return count
