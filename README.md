# 4.5SentinelValues
Handout looking at 3 examples of sentinel values.

4.5: Application: Processing Sentinel Values (Pages 158-160)

• A sentinel value denotes the end of a data set, but it is not part of the data set.

• A sentinel values serves as a signal for termination.

Example 1: Compute the average of a set of salary values. Use -1 as the sentinel value.

Inside the loop, we read an input. If the input is not -1, we process it. In order to compute the average, we need the total sum of all
salaries, and the number of inputs.
```java
import java.util.Scanner;
/** This program prints the average of salary values that are terminated with a sentinel
*/
public class SentinelDemo
{
public static void main(String[] args)
{
double sum = 0;
int count = 0;
double salary = 0; //Initialize salary because when the loop is entered for
// the first time, no data value has been read.
System.out.print(“Enter salaries, -1 to finish: “);
Scanner in = new Scanner(System.in);
//Process data until the sentinel is entered
while(salary != -1){
salary = in.nextDouble();
if(salary != -1)
{
sum = sum + salary;
count++;
}
}
//Compute and print the average
if(count > 0) {
double average = sum / count;
System.out.println(“Average salary: “ + average);
}
else {
System.out.println(“No data”);
}
}
}
```
Example 2: If you have the case which any number (positive, negative, or zero) can be an acceptable output, you must use a sentinel
that is not a number (such as a letter – example the letter Q).

We can use the condition: in.hasNextDouble()

If in.hasNextDouble() is false, then the next input is not a floating-point number. Therefore, you can read and process a set of inputs
with the following loop:
```java
/*Example 2: While Loop – Check in.hasNextDouble()*/
System.out.print(“Enter values, Q to quit: “);
While (in.hasNextDouble()) {
Value = in.nextDouble();
Process value
}
Example 3: - While Loop – Using a String as a Sentinel Value
/*Example output:
Type a line (or "quit" to exit): hello
Type a line (or "quit" to exit): this is a line
Type a line (or "quit" to exit): quit
You typed a total of 19 characters.
*/
import java.util.*; // for Scanner
public class Sentinel {
public static final String SENTINEL = "quit";
public static void main(String[] args) {
Scanner console = new Scanner(System.in);
// read text from scanner until we see the sentinel
// any variable(s) used in your while loop test must be declared BEFORE
// the loop header
int sum = 0;
 // fencepost loop; move one "post" out of the loop
 // "posts" - prompt/read a line
// "wires" - add the line lengths to a cumulative sum
System.out.print("Type a line (or \"" + SENTINEL + "\" to exit): ");
String response = console.nextLine();
while (!response.equals(SENTINEL)) {
sum += response.length();
System.out.print("Type a line (or \"" + SENTINEL + "\" to exit): ");
response = console.nextLine();
}
System.out.println("You typed a total of " + sum + " characters.");
}
}
```
Questions: Write problems 1-5 in a word doc. Write #6 as a java program. Upload the word doc and java program to
GitHub. Check Remind for the link titled: 4.5 Sentinel Values

1. What does the SentielDemo.java program print when the user immediately types -1 when prompted for a value?
2. Why does the SentinelDemo.java program have two checks of the form salary != -1?
3. What would happen if the declaration of the salary variable in Sentinel Demo.java was changed to: double salary
=-1?
4. In the second example, the user was prompted with “Enter values, Q to quit.” What happens when the user
enters a different letter?
5. What is wrong with the following loop for reading a sequence of values?
System.out.print(“Enter values, Q to quit: “);
do {
double value = in.nextDouble();
sum = sum + value;
count++;
}
while (in.hasNextDouble());
6. Currency conversion. Write a program that first asks the user to type today’s price for one dollar in Japanese yen,
then reads U.S. dollar values and converts each to yen. Use 0 as a sentinel.
