# Q. 2011
## Final Value of Variable After Performing Operations

### Code !

        class Solution {
            public static int finalValueAfterOperations(String[] operations) {

		        int X = 0;

		        for (int i = 0; i < operations.length; i++) {
			        if (operations[i].equals("++X") || operations[i].equals("X++")) {
                        X = X + 1;
                    }
                    else {
				        X = X - 1;
			        }
		        }
		        return X;
	        }
        }

### Explaination !
- In Line 3, we have initialized the variable X with value 0.
- In Line 4, we have started for loop to traverse over the array values.
- In Line 5 to 10, we are checking whether our conditions satisifies or not using if else conditions and here we are using .equals method because we are comparing string values.
- In Line 12, we rae returning the final value of X after performing all the operations.