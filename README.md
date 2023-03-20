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
