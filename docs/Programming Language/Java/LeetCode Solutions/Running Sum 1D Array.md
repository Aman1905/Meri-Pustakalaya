# Q. 1480
## Running Sum of 1d Array

### Code !

        class Solution {
            public static int[] runningSum(int[] nums) {

		        int n = nums.length;
		        int x = 0;
		        int[] ans = new int[n];

		        for (int i = 0; i < n; i++) {
			        x = x + nums[i];
			        ans[i] = x;
		        }

		        return ans;
	        }
        }

### Explaination !
- In Line 3, we have taken length of the nums array and stored in variable n.
- In Line 4, we have initialized a variable x of value 0.
- In Line 5, we have initialized an array ans of the same length of nums.
- In Line 6, for loop is started so as to traverse all over the array nums and then storing each value of nums in the variable x and then updating the ans array.
- In Line 7, we are returning the new array ans as the updated one.