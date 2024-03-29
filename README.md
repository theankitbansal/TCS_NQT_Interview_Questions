# TCS_NQT_Interview_Questions
Interview questions 

1. Name the pillars of Object-Oriented Programming. Is C++ an Object-Oriented programming language? Is C++ a purely object-oriented programming language?

The 4 pillars of object-oriented programming are encapsulation, abstraction, inheritance, and polymorphism. 

Abstraction: Abstraction means hiding the details from the user. For instance, when we build any application, we only let the user interact with it using buttons. We never let the user know what happens behind the clicks of the buttons.
Encapsulation: As the name suggests, this means encapsulating different kinds of data into a single entity. For instance, when we make a class, we encapsulate the data and member functions into that single class.
Inheritance: When a class inherits from another class, it shares the properties of the first class. For example, if we make a Student class, it inherits the class People as a student have all the properties of People like a student walks, talks, etc., and apart from it, the Student has its own properties like enrollment number, subjects, etc.
Polymorphism:: The word “poly” means many and the rod “morph” means form. This means that polymorphism means showing many forms. Polymorphism can be run-time or compile-time. Examples of polymorphism are function overloading and function overriding.
Yes, C++ is an Object-Oriented programming language as we can create classes and objects and C++ can implement all the 4 pillars of OOPS. However, C++ is not a purely object-oriented programming language. This is because a purely object-oriented programming language is such a language where all the functions are written inside a class and there are no primitive data types. Everything is an object in a pure object-oriented programming language.

2. Write a program to swap two numbers. You cannot use a third variable and you cannot use the + (plus), - (minus),* (multiply),/ (divide) operators.

The solution is using the XOR operator. Following is the C++ code for the same.


C++ Program

#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

void swap(int &x, int &y) {
	x = x ^ y;
	y = x ^ y;
	x = x ^ y;
}

int main() {
	// Your code goes here;
	int x , y;
	cin >> x >> y;
	
	cout<<"Before swapping, x = " << x <<" y = " << y<<"\n";
	swap(x,y);
	
	cout<<"After swapping, x = " << x <<" y = " << y<<"\n";
	
	return 0;
}
Sample Input:

10 20
Sample Output:

Before swapping, x = 10 y = 20
After swapping, x = 20 y = 10

3. Write a program to perform Binary Search on an array.

The binary search algorithm is used to find an element in a sorted array. It is an optimized searching algorithm as the linear search scans all the elements of the array and the searching time for the linear search thus becomes O(N). However, the searching time of Binary Search is O(log2N). This is because in an average case, only log2N elements of an array are compared. We start by checking the middle element of the array. If the middle element of the array is our answer, we have found the element. If the number that we are searching for is greater than the middle element, it will be on the right half of the array as the array is sorted. So, apply binary search on the right half. If the number that we are searching for is smaller than the middle element of the array, we will apply the binary search on the left half of the array. Following is the C++ program for binary search.

C++ Program for Binary Search

#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int binary_search(int arr[], int n,int target) {
	int lo = 0;
	int hi = n-1;
	
	while(lo <= hi) {
		int mid = lo + (hi-lo)/2;
		
		if(arr[mid] == target) return mid;
		else if(arr[mid] < target) lo = mid + 1;
		else hi = mid -1; 
	}
	
	return -1;
}

int main() {
	// Your code goes here;
	int arr[] = {10,12,25,36,42,58,97};
	if(binary_search(arr,7,12) == -1) {
		cout<<"Element was not found";
	} else {
		cout<<"Element was found at index " << binary_search(arr,7,12);
	}
}
Output: 

Element was found at index 1

4. Write a program to find whether a number is even or odd. You are not allowed to use any arithmetic operator i.e. plus (+), minus (-), multiply (*), divide(/), and modulus (%) are not allowed.

An even number in binary form will always have its Least Significant Bit (LSB) = 0. So, if we take the XOR of this number with 1, the answer will become one greater than the number itself. This is because 0 XOR 1 is 1 so, LSB will become 1 from 0 i.e. increment in the value by 1. So, we can say that if a number (N) is an even number then, if N ^ 1 =  N + 1  else the number would be an odd number. So, the C++ program to solve the problem is given below.

C++ Program

#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

bool is_even(int N) {
	if((N ^ 1) == N + 1) return true;
	else return false;
}

int main() {
	// Your code goes here;
	int N;
	cin>>N;
	
	if(is_even(N)) cout<<"The number is even";
	else cout<<"The number is odd";
}
Sample Input (Even Number):

10
Output:

The number is even
Sample Input (Odd Number):

9
Output:

The number is odd.

5. What is fragmentation? What does Linked List have to do with it?

We know that when we use arrays, we use sequential memory, i.e. the memory is used contiguously. Now, let us say that we have a large size array and we don’t have that much sequential memory. So, we won’t be able to store that data. Even if the memory is available, it is not available contiguously, but rather in fragments and we are not able to utilize this. This is called fragmentation.

	![image](https://user-images.githubusercontent.com/81725794/184070886-932380b9-f66e-4ede-a813-93e3654e73a2.png)

So, we can use a linked list to store the data as it does not require contiguous memory and thus solves the problem of fragmentation. In a linked list, data is stored in a node that also stores the pointer to the next node as the data is not contiguous and the next node can be present anywhere in the memory.
	
![image](https://user-images.githubusercontent.com/81725794/184070927-cc422233-0ed8-4ec9-a726-9ecc504ea54a.png)

6. List some linear and some non-linear data structures.
	
Linear Data structures: Arrays, Linked Lists, Stacks, Queues, and Dequeues, are all linear data structures.
Non-Linear Data structures: The non-linear data structures can further be categorized as circular and non-circular. Some circular data structures are Circular Queue, Circular Dequeue, Circular Linked List, etc. Some non-circular data structures are Trees, Graphs, Priority queues, etc.
	
7. List some major roles performed by an Operating System.
	
An operating system performs various roles. Some of the examples are as follows:

Resource Governor: The OS acts as a resource governor so that there is no load on the system. It allocates and deallocates the resources to the processes and also handles the synchronization of these resources among various processes.
Process Management: OS uses various Scheduling algorithms to manage the processes and their execution. This is done to increase the efficiency of the CPU so that it is never idle and the processes keep on executing.
Storage Management: OS acts as a storage manager bus using its File System. The data of the user is stored in the form of files and directories.
Memory Management: Memory management and storage management are confused with each other. However, the storage management concerns the file system and storage of the data in the Computer, the memory management means managing the memory allocation to the processes at the time of execution. Which process should be kept in the Ready Queue, which is in the Waiting Queue (both these queues are inside RAM only).
Privacy and Security: Privacy and security from any threats or viruses are also the responsibility of the OS. However, inter-process security is also the responsibility of the OS.
	
8. Can we override the private methods?	
	
No, we can’t override the private methods. The private methods are those methods that have a scope only within the same class. Since they cannot be accessed outside the class even by a sub-class, there is no way to override the private methods.

9. List some comparisons and similarities between the Java and C++ programming languages.
	
Java and C++ are both Object-Oriented Programming languages. However, everything in Java has to be inside a class, whereas this is not the case with C++. C++ has structures that are similar to classes but are used in Procedural Oriented Programming and not Object-Oriented Programming. Java does not have structures. Java has interfaces and C++ does not. Also, in C++, multiple inheritance is supported while it is not supported in Java. 

C++ is fast as compared to Java because C++ is a compiled language, whereas Java is a hybrid language i.e. it is both compiled as well as interpreted. Also, Java uses JVM to run whereas C++ runs directly using the OS. Hence, Java is platform-independent whereas C++ is platform-dependent. 

Java has Wrapper classes for each primitive data type. So, even though Java is not purely Object Oriented, it is possible to write a pure Object-Oriented Program in Java whereas it is not possible to do so in C++.

10. What is DOM?
	
DOM stands for Document Object Model. It is an API (Application Programming Interface) that is used to access and change the contents of HTML elements. It provides a hierarchical structure of the web page that makes it easy to access the elements, their parents, their siblings and their children.

11. Difference between Process and Thread.
![Screenshot (985)](https://user-images.githubusercontent.com/81725794/184279465-dce33cfa-d8f6-46b1-ad28-0329886bdaea.png)


12. Difference between user-level thread and kernel-level thread.

![Screenshot (986)](https://user-images.githubusercontent.com/81725794/184279491-d081f494-ca4b-4f8a-a386-f7b2562d973f.png)

13. What is the relation between the pages and frames in the OS?

In OS, paging is the method of dividing each process into small segments called pages and the main memory is also divided into the frames so that each frame can accommodate one data page. Hence, the relation between pages and frames is

Size of page = Size of frame

14. What is TCP/IP Protocol?

TCP stands for Transfer Control Protocol. The TCP is a connection-oriented protocol implemented at the Transport Layer of the OSI Model. TCP is responsible for breaking the data into the form of small frames called framing and later, at the receiver end, it also reassembles the frames back into the sequence to get the data back. 

IP stands for Internet Protocol. It is present at the Network Layer of the OSI model. IP is not reliable and it is a connectionless model. IP is responsible for sending and receiving the data that is broken into the form of frames by the TCP. The IP is combined with TCP to form a reliable data sending-receiving Protocol.

15. Write an SQL query to print the current date.

The SQL Query to print the current date is: GetDate()

16. Write an SQL Query to select all those entries from the table STUDENTS, whose name is “Rahul”.
The SQL Query to do so is

SELECT * FROM STUDENTS WHERE NAME = “Rahul”
	
17. What do you know about DCL?
	
DCL means Data Control Language. DCL is responsible for managing the access and permissions to a DBMS. DCL helps in deciding which part of the Database should be accessed by which user. The 2 major commands in DCL are :

GRANT: This command is used to grant privileges to the Objects of the database for a user. It helps one user to grant certain permissions to the other users.
REVOKE: This command is used to withdraw the privileges for the objects of the database that have been granted to a user.
	
18. Can constructors be overridden?

No, constructors are not overridden. The sub-class constructors have to call the super-class constructor for their creation as they inherit from the super-class. Hence, the constructors cannot be overridden.

19. Do you know why the main() method is static in Java?
	
The main() method, like every other method in Java, is also inside a class. Now, when we compile or run the Java program, we do not create an object of the class containing the main() method. So, we have to make sure that the main() method can be accessed without creating an object of the main() class. Hence, the main() method is static because the static methods belong to the class and not to a particular object.

20. Write a program to print the right-angled triangle pattern as shown below for any value of N input by the user.
	
For N = 5

*
**
***
****
*****
Let us observe the pattern carefully. We can see that in the 1st row, there is only 1 star and in the second row, there are 2 stars, and so on. This means that in the ith row, we are printing i number of stars. Following is the C++ program for the same.

C++ Program

#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;


int main() {
	// Your code goes here;
	int N;
	cin>>N;
	
	for(int i=1;i<=N;i++) {
		for(int j=1;j<=i;j++) {
			cout<<"*";
		}
		cout<<"\n";
	}
}
Sample Input: 7	

	![image](https://user-images.githubusercontent.com/81725794/184279677-5eeca312-98cb-4793-8528-db86bd53a7e9.png)
