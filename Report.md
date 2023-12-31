Part 1:

Step 1 Student Post:

Title: Issue with Java Program - Unexpected Behavior

Content:

Hi everyone,

I've written a simple Java program (NumberSum.java) that reads numbers from a file (numbers.txt) and calculates their sum. 

NumberSum.java:
```
import java.io.*;
import java.util.*;

public class NumberSum {
    public static void main(String[] args) {
        try {
            File file = new File("numbers.txt");
            Scanner scanner = new Scanner(file);

            int sum = 0;
            while (scanner.hasNextInt()) {
                int number = scanner.nextInt();
                sum += number;
            }

            System.out.println("Sum: " + sum);
            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found.");
        }
    }
}

```
numbers.txt:
```
10
20
30
not_a_number
40
```

However, when I run the program using my Bash script (run.sh), it's not showing the expected result. Instead, it just displays "60" (which is inccorect) without any error message. 
Here's a screenshot of the terminal output after running the script:

![Image](lab5error.jpg)

I suspect the issue might be related to the way the program reads the file or maybe an error in the file content. Can anyone help me figure this out?

Step 2 TA Response:

Context:

Hi,

It looks like the program might be encountering an unexpected value in your numbers.txt file. 
Can you try running the program with the -ea flag to enable assertions, and also add a print statement in your while loop to see what value it reads right before it stops? 
This should give us more insight into where the problem might be.

Step 3 Student Follow Up:
   
Content:
Thanks for the suggestion! I added a print statement and ran the program with the -ea flag. Here's the updated screenshot of my terminal:

![Image](lab5update.jpg)

It seems like the program is failing to handle a non-integer value in the file. The bug is in the file reading part of the code.

Steo 4 Final Summary:

File & Directory Structure:

NumberSum.java: Java program file, run.sh: Bash script to compile and run the Java program, numbers.txt: Input file containing numbers

Contents of Each File Before Fixing the Bug:

NumberSum.java: (Java code content), run.sh: (Bash script content), numbers.txt: Contained a non-integer value

Commands to Trigger the Bug:

./run.sh

Solution:

Edit numbers.txt to ensure it only contains integer values.

Part 2:


During the second half of the quarter, We explored the basics of Vim, a powerful text editor known for its efficiency. 
Grasping its modal nature and keyboard-focused commands was initially challenging, but it quickly became a game-changer for my coding efficiency. 
Vim's seamless navigation and editing capabilities, without the need for a mouse, significantly streamlined my workflow, 
revealing the practical benefits of mastering a text-based interface.
