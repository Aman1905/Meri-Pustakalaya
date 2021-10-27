# 1929
## Array Concatenation

### Code !

        class Solution {
            public int[] getConcatenation(int[] nums) {

                int n = nums.lengt
                int[] ans = new int[2 * n];
                
                for (int i = 0; i < n; i++) {
                    ans[i] = nums[i];
                    ans[i + n] = nums[i];
                }

		    return ans;
	    }
    }


### Explaination !

- In Line 3, outer loop we have started which will iterate over the whole array starting from the pos 0 to the last number
- In Line 4, inner loop is starting which will start from the pos i+1, i.e. whatever the position of ith variable is it will always start from the next number.
- In Line 5 we are checking whether as per the quest, nums[i] + nums[j] == target or not, if yes then returning the ith and jth value and if not then returning the blank array.