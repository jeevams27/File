 <h1>File</h1> 

## Aim:
To write a C# program to store the student details in file using structure concept.

## Algorithm:
### Step1:
Create a structure for student details.
### Step2:
Create a file using FileStream.
### Step3:
Get the number of students and their details from user.
### Step4:
Define a function to write the details of student into the created file.
### Step5:
Pass the details of student to the function.
### Step6:
File has been created and written with student details.

## Program:

```
Developed By: Jeeva MS
Reg No: 212221230040
```
```c#
using System;
using System.IO;
struct student
{
    public string name;
    public int age;
    public string department;
    public int percentage;
};
class HelloWorld
{

    void writer(string name, int age, string department, int percentage, int i)
    {
        FileStream fs = new FileStream("file.txt", FileMode.Append, FileAccess.Write);
        StreamWriter sw = new StreamWriter(fs);
        sw.WriteLine("Name of the student {0} is {1}", i, name);
        sw.WriteLine("Age of the student {0} is {1}", i, age);
        sw.WriteLine("Department of the student {0} is {1}", i, department);
        sw.WriteLine("percentage of the student {0} is {1}", i, percentage);

        sw.Close();
        fs.Close();
    }
    static void Main()
    {
        int n, i;
        FileStream fs = new FileStream("file.txt", FileMode.Create, FileAccess.Write);
        fs.Close();
        Console.WriteLine("Enter the number of Students:");
        n = Convert.ToInt32(Console.ReadLine());
        student[] s = new student[n];
        for (i = 0; i < n; i++)
        {
            Console.WriteLine("Enter the name:");
            s[i].name = Console.ReadLine();
            Console.WriteLine("Enter the age:");
            s[i].age = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Enter the department:");
            s[i].department = Console.ReadLine();
            Console.WriteLine("Enter the percentage:");
            s[i].percentage = Convert.ToInt32(Console.ReadLine());
            HelloWorld hw = new HelloWorld();
            hw.writer(s[i].name, s[i].age, s[i].department, s[i].percentage, i + 1);
            Console.WriteLine();
        }
    }
}
```
## Output:
https://user-images.githubusercontent.com/94279791/282307209-8b5c1cea-1bc5-43bd-82a6-f4ae30cb4d4e.png

## Result:
Thus a C# program to store the student details in file using structure concept is implemented successfully.
