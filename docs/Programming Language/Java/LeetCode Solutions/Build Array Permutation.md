# Q. 1920
## Build Array from Permutation

### Code !

        class Solution {
            public int[] buildArray(int[] nums) {

		        int n = nums.length;

		        int[] ans = new int[n];

		        for (int i = 0; i < n; i++) {
			        ans[i] = nums[nums[i]];
		        }

		    return ans;
	    }
    }

### Explaination !

- In Line 3, we have taken the length of array nums.
- In Line 4, we have initialized new array ans of the same length of nums array
- In Line 5, we have started for loop so as to traverse each num in the nums array and then considering the value of that ith number's as position of the nums array and then storing that value in the ans array.
- At last just return the ans array.