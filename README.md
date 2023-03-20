# Design a Prime Number between 2 to 30

          public static void main(String args[]) {
              for (int i = 2; i <= 30; i++) {
                if (isPrime(i)) {
                  System.out.print(i);
                }
              }
            }

            public static boolean isPrime(int n) {
              if (n <= 1) {
                return false;
              }
              for (int i = 2; i <= Math.sqrt(n); i++) {
                if (n % i == 0) {
                  return false;
                }
              }
              return true;
            }
            
# Swap 2 numbers without using 3rd variable

                    int x=5;
                    int y=7;
                    x = x + y;   
                    y = x - y;   
                    x = x - y;   
                    System.out.print("X Value:"+ x);
                    System.out.print("Y Value:"+ y);

# Design a program to display magic number, accept a number and check it is a magic number or not.

                   int number = 109;
		if (((number - 1) % 9) == 0)
			return true;
		else
			return false;
			
# Display a L shape * symbol

		for (int i = 0; i < 10; i++) {
			if (i < 4) {
				System.out.println("*");
			} else {
				System.out.print("* ");
			}
		}
