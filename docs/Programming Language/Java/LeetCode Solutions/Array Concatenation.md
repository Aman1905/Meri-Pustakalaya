# 1929
## Array Concatenation

### Code !

        class Solution {
            public int[] getConcatenation(int[] nums) {

                int n = nums.length;
                int[] ans = new int[2 * n];
                
                for (int i = 0; i < n; i++) {
                    ans[i] = nums[i];
                    ans[i + n] = nums[i];
                }

		    return ans;
	    }
    }


### Explaination !

- In Line 3, we have taken the length of the nums array in variable n.
- In Line 4, we have created a new array (ans) with the length of 2n.
- In Line 5, we have taken a for loop which is traversing in the nums array and picking each number one by one.
- In Line 6, we are assigning that ith number of the nums array to the ith position of the ans array
- In Line 7, we are re-assigning the ith number of the nums array to the (i+n)th position of the ans array for the concatenation