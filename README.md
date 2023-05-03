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
			if (i < 5) {
				System.out.println("*");
			} else {
				System.out.print("* ");
			}
		}
		
		
# Print the first letter of each word 

public class FirstLetterOfEachWord {

		public static void main(String[] args) {
				List<String> words = Arrays.asList("apple", "banana", "cherry", "date", "elderberry");

				StringBuilder result = new StringBuilder();

				// use a Consumer to append the first letter of each word to the StringBuilder
				Consumer<String> appendFirstLetter = word -> result.append(word.charAt(0));

				words.forEach(appendFirstLetter);

				// print the resulting string
				System.out.println(result.toString()); // prints "abcde"
			}

		}
		
		
# Functional Interface

			public class FuncInterface {

				public static void main(String[] args) {
					SupplierExample();
					ConsumerExample();
					PredicateExample();
					FunctionExample();
				}

				public static void SupplierExample() {
					Supplier<Integer> randomInt = () -> new Random().nextInt();
					System.out.println(randomInt.get()); // prints a random integer

				}

				public static void ConsumerExample() {
					List<String> names = Arrays.asList("Alice", "Bob", "Charlie");
					Consumer<String> printName = name -> System.out.println(name);
					names.forEach(printName); // prints each name in the list
				}

				public static void PredicateExample() {
					List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
					Predicate<Integer> isEven = number -> number % 2 == 0;
					List<Integer> evenNumbers = numbers.stream().filter(isEven).collect(Collectors.toList());
					System.out.println(evenNumbers); // prints [2, 4]

				}

				public static void FunctionExample() {
					List<String> names = Arrays.asList("Alice", "Bob", "Charlie");
					Function<String, Integer> nameLength = name -> name.length();
					List<Integer> nameLengths = names.stream().map(nameLength).collect(Collectors.toList());
					System.out.println(nameLengths); // prints [5, 3, 7]
				}

			}
			
# Map to String 

			public class MapToString {
				 public static void main(String[] args) {
					Map<String, Integer> map = new HashMap<>();
					map.put("apple", 1);
					map.put("banana", 2);
					map.put("cherry", 3);
					map.put("date", 4);
					map.put("elderberry", 5);

					StringBuilder result = new StringBuilder();

					// append each key-value pair to the StringBuilder
					for (Map.Entry<String, Integer> entry : map.entrySet()) {
					    result.append(entry.getKey()).append(": ").append(entry.getValue()).append(", ");
					}

					// remove the trailing comma and space
					if (result.length() > 0) {
					    result.setLength(result.length() - 2);
					}

					// print the resulting string
					System.out.println(result.toString()); // prints "apple: 1, banana: 2, cherry: 3, date: 4, elderberry: 5"
				    }

			}


# Order Filter

			class Order {
			    private int id;
			    private String status;
			    private double price;

			    public Order(int id, String status, double price) {
				this.id = id;
				this.status = status;
				this.price = price;
			    }

			    public int getId() {
				return id;
			    }

			    public String getStatus() {
				return status;
			    }

			    public double getPrice() {
				return price;
			    }

			    @Override
			    public String toString() {
				return "Order{" +
					"id=" + id +
					", status='" + status + '\'' +
					", price=" + price +
					'}';
			    }
			}

			// Main class
			public class OrderFilter {
			    public static void main(String[] args) {
				// Create a list of orders
				List<Order> orders = new ArrayList<>();
				orders.add(new Order(1, "ACCEPTED", 5000));
				orders.add(new Order(2, "COMPLETED", 15000));
				orders.add(new Order(3, "ACCEPTED", 20000));
				orders.add(new Order(4, "PENDING", 12000));

				// Define lambda expression for filtering orders
				orders.stream()
					.filter(order -> order.getPrice() > 10000 && (order.getStatus().equals("ACCEPTED") || order.getStatus().equals("COMPLETED")))
					.forEach(System.out::println);
			    }
			}
			
# Remove Word

			public class RemoveWord {
				public static void main(String[] args) {
					List<String> words = new ArrayList<>(Arrays.asList("apple", "banana", "cherry", "date", "elderberry"));

					// remove words with odd lengths
					words.removeIf(word -> word.length() % 2 != 0);

					// print the list of remaining words
					System.out.println(words); // prints [banana, elderberry]
				}
			}
			
			
# Replace Upper case

			public class ReplaceUppercase {

				public static void main(String[] args) {
				List<String> words = new ArrayList<>(Arrays.asList("apple", "banana", "cherry", "date", "elderberry"));

				// use a UnaryOperator to replace each word with its uppercase equivalent
				UnaryOperator<String> toUpperCase = String::toUpperCase;

				words.replaceAll(toUpperCase);

				// print the list of uppercase words
				System.out.println(words); // prints ["APPLE", "BANANA", "CHERRY", "DATE", "ELDERBERRY"]
			    }

			}
			
# Arithmatic Operations using Interface

		public class ArithmeticOperation {

			public static void main(String[] args) {
				double x = 10.0;
				double y = 5.0;

				// Define lambda expressions for each arithmetic operation
				ArithmeticOperationIfc add = (a, b) -> a + b;
				ArithmeticOperationIfc subtract = (a, b) -> a - b;
				ArithmeticOperationIfc multiply = (a, b) -> a * b;
				ArithmeticOperationIfc divide = (a, b) -> a / b;

				// Perform arithmetic operations
				double sum = add.perform(x, y);
				double difference = subtract.perform(x, y);
				double product = multiply.perform(x, y);
				double quotient = divide.perform(x, y);


				// Print the results
				System.out.println("Sum: " + sum);
				System.out.println("Difference: " + difference);
				System.out.println("Product: " + product);
				System.out.println("Quotient: " + quotient);
			}
		}

		interface ArithmeticOperationIfc {
			double perform(double x, double y);
		}
		
# Thread Example


			public class ExampleThread {
				public static void main(String[] args) {
					List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

					// create a new thread that prints the numbers from the list
					Thread printNumbersThread = new Thread(() -> {
						// use a Consumer to print each number
						Consumer<Integer> printNumber = System.out::println;

						numbers.forEach(printNumber);
					});

					// start the thread
					printNumbersThread.start();
				}
			}
			
# Stream Examples


			public class StreamFunction {
				public static void main(String[] args) {
					FindFirstNumberIsOne();
					FindDuplicateElements();
					FindFirstElement();
					FindElementsCount();
					FindMaxValueElement();
					SortByDesc();
				}

				private static void FindFirstNumberIsOne() {
					List<Integer> numbers = Arrays.asList(12, 156, 100, 34, 172, 19, 1);

					List<Integer> result = numbers.stream().filter(num -> String.valueOf(num).startsWith("1"))
							.collect(Collectors.toList());

					System.out.println(result);

				}

				private static void FindDuplicateElements() {

					List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 2, 5, 3, 6, 7, 8, 1);

					Map<Integer, Long> counts = numbers.stream().collect(Collectors.groupingBy(n -> n, Collectors.counting()));

					List<Integer> duplicates = counts.entrySet().stream().filter(e -> e.getValue() > 1).map(Map.Entry::getKey)
							.collect(Collectors.toList());



					System.out.println(duplicates);

				}

				private static void FindFirstElement() {
					List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

					Optional<Integer> first = numbers.stream().findFirst();

					if (first.isPresent()) {
						System.out.println("The first element is: " + first.get());
					} else {
						System.out.println("The list is empty.");
					}

				}

				private static void FindElementsCount() {
					List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

					long count = numbers.stream().count();

					System.out.println("The total number of elements is: " + count);
				}

				private static void FindMaxValueElement() {
					List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

					Optional<Integer> max = numbers.stream().max(Integer::compare);

					if (max.isPresent()) {
						System.out.println("The maximum value element is: " + max.get());
					} else {
						System.out.println("The list is empty.");
					}

				}

				private static void SortByDesc() {
					List<Integer> numbers = Arrays.asList(3, 5, 2, 1, 4);

					List<Integer> sorted = numbers.stream().sorted(Comparator.reverseOrder()).collect(Collectors.toList());

					System.out.println("The sorted list in descending order is: " + sorted);
				}
				
				private static void FindFirstNonRepeatedCharecterFromString() {
					String str = "yosiya";

					String[] strCharList = str.toLowerCase().split("");

					List<String> strList = Arrays.asList(strCharList);

					Map<String, Long> charCountMap = strList.stream()
							.collect(Collectors.groupingBy(str1 -> str1, Collectors.counting()));

					System.out.println(charCountMap);

					for(int i=0; i<strList.size(); i++)
						if (charCountMap.get(strList.get(i)) == 1) {

							System.out.println("The First Non Repeated Charecter is ::" + strList.get(i));
							break;
						}


				}								
			}
