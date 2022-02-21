## A Simple Report Card in Java

I leanrt Java in the last semister, so I thought I should make a project. 
I searched on Google for Java projects and I found:

**Write a program to take marks of 2 subjects from user and display the Total, Percentage, Highest Marks, Average and Remarks.**

It was not that tough, so this is how I made it.

First, I imported this library for taking input from user:

    import  java.util.Scanner;
Then, I created the file named 'marks'. I know this file name don't make sense but it's ok.

Java starting Template: 

    public  class  marks {
    public  static  void  main(String  args[]) { 
	    // Code Here
	    }
    }
Starting with my code, I defined [Scanner Class](https://www.w3schools.com/java/java_user_input.asp) a variable 'sc' to make it easy to get input from user

    try (Scanner  sc = new  Scanner(System.in)) {
    	// Code Here
    }
I put the above variable in 'try' because Visual Studio was giving errors.

Next, I displayed in the console what I want from them:

    System.out.println("Enter the marks of 2 subjects (out of 100)");

Then, I asked the two input from user

    System.out.println("Enter the marks of subject 1:");  
    int  sub1 = sc.nextInt();
    
    System.out.println("Enter the marks of subject 2:");
    int  sub2 = sc.nextInt();
'sc' is the variable name that I declared above and `nextInt()` is the function for accepting the values in integer which will be store in the variable 'sub1' and 'sub2' respectively.

Okay, here comes the important step, as you know you can't score more than 100 in a subject, doesn't matter how brilliant you are. So, I have to make sure that, user can't add number greater than 100.

This condition make sure that the entered value is less than or equal to 100.

    if (sub1 <= 100 && sub2 <= 100) {
	    // This code will be executed if the condition is true
    } else{
	    // This code will be executed if the condition if false
    }
Wow, great! All the measures taken, users also can't give anyother input except number, if they try, they will get an error.

Now time for the real code:

    int  total = sub1 + sub2;
    System.out.println("Total = " + total);
    
This will add the two values and print the Total.

This code will find the percentage, 'float' is used because the answer may be in decimal and it is also multiplied by 'float' to covert it into float datatype. How to convert [Integer into Float.](https://www.c-sharpcorner.com/article/the-complete-java-type-casting-tutorial/)

    float  percent = (float) total / 200 * 100;
    System.out.println("Percentage = " + percent);
    
Then, a simple if-else statement to get the highest number:

    if (sub1 > sub2) {
    System.out.println("Highest marks scored is " + sub1);
    } else {
    System.out.println("Highest marks scored is " + sub2);
    }
    
For finding average, just take the toatal and divide it by 2:

    float  avg = (float) total / 2;
    System.out.println("Average is " + avg);

Then, again an if-else to display remakrs. If the marks is 50 or less than that, then it will display 'You need to work hard!'. If the marks is above 80 or equal and less than 90 then it will show 'Good Marks', if it is above 90 then it will show 'Excellent'. Preety Simple.

    if (percent <= 50) {
    System.out.println("Remarks: You need to work hard!");
    } else  if (percent >= 80 && percent <= 90) {
    System.out.println("Remarks: Good Marks :)");
    } else  if (percent >= 90) {
    System.out.println("Remarks: Excellent");
    } else {
    System.out.println("Remarks: Good");
    }
    
So, that's how I made it. It was really fun. By the way, thanks for visiting and reading :)

Full Source Code:

    import  java.util.Scanner;
    
      
    
    public  class  marks {
    
    public  static  void  main(String  args[]) {
    
      
    
    try (Scanner  sc = new  Scanner(System.in)) {
    
      
    
    System.out.println("Enter the marks of 2 subjects (out of 100)");
    
      
    
    System.out.println("Enter the marks of subject 1:");
    
    int  sub1 = sc.nextInt();
    
      
    
    System.out.println("Enter the marks of subject 2:");
    
    int  sub2 = sc.nextInt();
    
      
    
    if (sub1 <= 100 && sub2 <= 100) {
    
      
    
    // Total
    
      
    
    int  total = sub1 + sub2;
    
    System.out.println("Total = " + total);
    
      
    
    // Percentage
    
      
    
    float  percent = (float) total / 200 * 100;
    
    System.out.println("Percentage = " + percent);
    
      
    
    // Highest Marks
    
      
    
    if (sub1 > sub2) {
    
    System.out.println("Highest marks scored is " + sub1);
    
    } else {
    
    System.out.println("Highest marks scored is " + sub2);
    
    }
    
      
    
    // Average
    
      
    
    float  avg = (float) total / 2;
    
    System.out.println("Average is " + avg);
    
      
    
    // Remarks
    
    if (percent <= 50) {
    
    System.out.println("Remarks: You need to work hard!");
    
    } else  if (percent >= 80 && percent <= 90) {
    
    System.out.println("Remarks: Good Marks :)");
    
    } else  if (percent >= 90) {
    
    System.out.println("Remarks: Excellent");
    
    } else {
    
    System.out.println("Remarks: Good");
    
    }
    
      
    
    } else {
    
    System.out.println("Values are Greator!");
    
    }
    
      
    
    }
    
      
    
    }
    
      
    
    }

Output: 
![java-project-simple-report-card-output](https://raw.githubusercontent.com/MayankVikash/mayankvikash.ml/gh-pages/assets/images/posts/java-marks-management/java-project-simple-report-card-output.gif)

Note: Currently, it supports only 2 subjects but I will update it to 15 subjects, I am working on it, will update here soon.

Made by [Mayank Vikash](https://mayankvikash.ml/)
