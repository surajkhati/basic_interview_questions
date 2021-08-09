Technical Round:-

	1. Explain your mini project.

		- The topic of my Mini-Project was created a semi-automated Attendance Tracking System using Face Recognition. I felt that manual attendance taking is quite prone to proxy-errors or sometimes errors on the part of the lecturer taking attendance. It also consumes valuable class time.

		- I built the entire project from scratch in Python. I used OpenCV for dealing with the webcam and giving visual feedback. Face_Recognition is a library specifically built for recognizing and encoding faces into 128 landmarks. It comes with a pre-trained machine learning model and is easy to use with Python.

		- The system can be used in two ways - to build the database or to take attendance of an existing class. For building the database, the operator will have to put in the student's registration number and name, and the system will capture the student's face if properly visible.

		- The second way of using the system is to take attendance of an existing class. The machine will call the students and each student will have to show his/her face. It will then mark the attendance.

		- Limitation of my project is that the process can be made a bit faster if the system can recognize multiple faces at once. I will be working on creating an app, that a lecturer can use to click the picture of an entire class, which will then be sent to a server running a program.
		It will go through the picture and mark attendance to all the faces in the picture.

	- Problems I faced during building the project:-
		1. I had never before programmed a Facial Recognition project, so it was kind of a challenge for me to learn how Faces are detected and recognized. Thankfully I found a library that did all of that for me.

		2. Second problem was to design the system entirely from scratch. I did not want to take the help of any existing system as such, so it was kind of a challenge to me. I had to decide how the program would flow, how the images will be stored, how the logs would be stored, etc.

		3. Third biggest problem I faced was generating a PDF from the JSON log file. So I had to program in FPDF-compatible HTML that would render a table of student's attendance data, but I had to do it through a lot of trial and error, which took we almost an entire day to get the table right.

	2. What are your favrite subjects?
		- My favorite subjects are Microprocessors and Data Structures.

	3. What is Polymorphism?
		- Polymorphism is a concept, which says that the same entity should behave differently in different scenarios. Or, a message to be interpreted differently in different situations. In Greek, Poly means many and morphs means forms. So it means many forms.

		- Example - A person will have to behave like a student in a school/college, as a customer in a shop, as an employee at work, etc.

		- Binding: process of converting identifiers into address. Done for each variable and function. For functions, it means matching the call with the right fucntion defintion by the compiler. Can take place during run-time or compile-time.

			- Early binding: Compiler directly associates an address to the fuction call. It replaces the call with a machine language instruction that tells the machine to jump to the address of the function. Default.

			- Late Binding: Compiler adds code that identifies the kind of object at runtime, then matches the call with the right function definition.

		- In C++, Polymorphism is divided into two types:-
			- Compile-time Polymorphism
				- Also known as static/early binding.
				- Can be achieved through:
					- Function Overloading
						- When there are multiple functions with the same name but different parameters, then these functions are said to be overloaded. Functions can be overloaded by change in the number/type of arguments.

					- Operator Overloading
						- Example:- '+' can be used for arithmetic addition as well as string concatenation.

						#include <iostream>
						using namespace std;

						class Complex {
							private:
								int real, imag;
							public:
								Complex(int r = 0, int i = 0) { real = r; imag = i; }

								Complex operator + (Complex const &obj) {
									Complex res;
									res.real = real + obj.real;
									res.imag = imag + obj.imag;

									return res;
								}

								void print() {
									cout << real + " i" << imag << endl;
								}
						};

						int main() {
							Complex c1(10, 5), c2(2, 4);
							Complex c3 = c1 + c2;
							c2.print();
						}

			- Run-time Polymorphism
				- Also known as late binding.
				- Function overriding.
					- Occurs when a derived class has a definition for one of the member functions of the base class. That base function is said to be overridden.

	4. What is Encapsulation?
		- Encapsulation is defined as wrapping up of data and methods that manipulate the data together in a single unit. It is one of the pillars of Object Oriented Programming.

		- Example:
			- In a company, if a Sales dept. employee wants to have a look at the quantity of raw materials bought by the company, he cannot get the information directly. He will have to write a request memo, which will then be given to a Production dept. employee who will fetch the required information and give it. Only the Production dept. employee (function) can access the Production data.

		- Encapsulation is implemented through classes which wrap the characteristics (data) and the behaviour (methods) together. Only the methods are public, which means to access the data, one will have to call the proper method that returns the data.

	5. What is UNIX? How is it different from Linux?

		UNIX:

			Unix is a propietary operating system developed in the 1960s at Bell Labs by Dennis Ritchie and Ken Thompson mainly.

			It is a multi-user, multitasking OS - where multiple users can use the system simultaneously, running various applications at the same time.

			It employs a simple phisophy which states that everything is a file. It treats the keyboard and the physical devices all as files and interacts with them through files.

		Linux:

			Linux on the other hand is an open-source operating system which is one of the most used OSs around the world. It finds its applications in almost every field, ranging from the military, to 
			serves, workstations, etc.

			It is essentially a Minix clone, which is an academic OS written by Andre Tannenbaum - which is also a UNIX clone.

			Linux is only the kernel. Whereas UNIX is the entire Operating System suite, complete with a GUI, drivers, etc.

	7. Name the major data structures used in RDBMS, Network Data Model, Hierarchical Data Model.

		RDBMS - Array of structures is majorly used to implement RDBMS.
		Network Data Model - Graphs
		Hierarchical Data Model - Trees

	8. What are the different types of pointers in C++?

		There are eight different types of pointers:-
			1. Null Pointer - A pointer which points nowhere, to NULL.

			2. Void Pointer - It is a pointer which has no data type associated with it. A void pointer can hold addresses of any type. Aka Generic Pointer. It can be later type-casted and dereferenced to any required type.

			malloc() and calloc() return void pointers.

				Dereferencing Void Pointer:-

				int a = 10;
				void *ptr = &a;

				cout << *(int*)a;

				-> meaning: a is being typecasted as (int*). And the outer * means dereferencing.

			3. Wild Pointer - uninitialized pointers. They point to some arbitrary location and can cause a program crash.

			4. Dangling Pointer - A pointer that points to a location which has been deleted is called a dangling pointer.

			5. Near Pointer - can store 16-bit addresses within current segment. We can acess only 64kb of data at a time.

			6. Far Pointer - can store 32-bit addresses, outside of current segment. Compiler allocates a segment register to store segment address, then another register to store offset within current segment.

			7. Huge Pointer - can also typically store 32-bit and outside segment. Segment not fixed, can be modified.


	9. What are Data Type ranges in C++?

		prefix:
			u = unsigned
			s = signed
			l = long
			sh = short

		Types 			Bytes		Range
		char 			1 			(-128, 127)
		uchar 			1 			(0, 255)
		schar 			1 			(-128, 127)
		int 			4 			(-2^(4*8), 2^(4*8) - 1)
		uint 			4 			(0, 2 * 2^32 - 1)
		sint 			4 			(-2^32, 2^32 - 1)
		ushint			2 			(0, 2 * 2^16 - 1)
		sshint 			2 			(-2^16, 2^16 - 1)
		lint 			8 			(-2^64, 2^64 - 1)
		slint 			8 			lint
		ulint 			8 			(0, * 2 * 2^64 - 1)
		llint 			8 			(-2^63, 2^63 - 1)
		ullint 			8 			(0, 2^128 - 1)
		float 			4
		double 			8
		ldouble 		12
		wchar_t 		2 or 4


	10. What is void data type?

		- Void is a data type in C/C++ which has no value and no operations. It represents a lack of type. It is generally used to indicate that the function does not return anything. Or it can also be used as a generic pointer which can be typecasted to any type.
	
	11. Which operator in SQL performs pattern-matching?
		LIKE operator, used in a WHERE clause.
		Example:
			SELECT * from table
			WHERE name LIKE pattern

		pattern:
			'a%' - starting with 'a'
			'%a' - ending with 'a'
			'%at%' - values that contain 'at'
			'_r%' - values having 'r' in the second position
			'a_%' - values starting with 'a' and at least 2 characters in length
			'a__%' - values starting with 'a' and at least 3 chars in length
			'a%0' - values that start with 'a' and end with 'o'

	12. What is the purpose of DESC in SQL?
		Used in ORDER BY DESC - meaning to sort data in descending order.

		ex.
			SELECT * FROM table
				ORDER BY attr DESC

	13. Give some advantages of DBMS.
		Advantages:-
			1. Data Integrity
			2. Data Consistency
			3. Reduced Data Redundancy
			4. Security against unauthorized access or accidental override
			5. Centralized access to data - meaning all applications have access to same consistent data
			6. Backup and Recovery

	14. What is NULL pointer?
		It is a pointer that does not point to any location in particular.
		Used to:-
			1. Initialize pointers not pointing to a particular location.
			2. Used in Linked Lists and etc. to indicate end.

	15. What is a static variable?


	16. You're from ECE, why IT industry?
		Since class 12th, I have been learning C++, and am deeply interested in Programming. All the skills I've honed are oriented towards programming. I chose ECE in order to learn how computer work internally, but my interests have always lied in programming.

	18. What is your favorite language?
		C++ and Python.

	19. What is Python. Features of Python.
		- Python is a high-level, interpreted, object-oriented programming language. It is a highly readable language, bearing close resemblance with the English language. It is easy to learn and work with.

		- The key features of Python are:
			- Python is an interpreted language. Hence, a Python program does not need to be compiled in order to be executed. It checks for errors in every line of the code.

			- Python is a dynamically-typed language, so a variable does not need to be declared with a specific type. The interpreter automatically identifies the type of variable by looking the type of value the variable holds.

			- Python follows a Procedural, as well as, OOP paradigm, although it lacks access specifiers. Python can classes, inheritance, abstraction and encapsulation, which makes it an OOP lanugage.

			- Python is a cross-platform language. It means that the program need not be compiled for every other system. If the machine has a Python interpreter, the program will run like on any other platform with little to no modifications at all.

			- Python has its applications is Machine Learning, Web Development, Data Science, Aeronautics and various other fields.

	20. What are the different types of loops?
		Two types of loops:-
			1. Entry-controlled
				- Condition is tested beforing executing loop statements
					- For-loop
					- While-loop
			2. Exit-controlled
				- Condition is tested after executing the loop statements

	22. Tell me about your project.
		- Morning

	24. Difference b/w C++ and Python.
		- Both are general-purpose programming languages.
		- C++ was started in the 60s, and Python in the 90s.
		- Both are OOP languages.

		- Python employs lesser lines of code to perform the same task in C++.
		- Python is an interpreted language, whereas C++ is a compiled language.
		- Python is slower compared to C++.
		- Python is a dynamically typed language, whereas C++ is a statically typed language.

	27. Write a program to print n fibbonacci terms.
		Python:
			def fib(n):
				if n in [0, 1]: return n
				else: return fib(n - 1) + fib(n - 2)

			if __name__ == '__main__':
				n = int(input())
				for i in range(1, n + 1):
					print(fib(i))

		C++:
			int fib(int n) {
				return (n == 0 || n == 1 ? n : fib(n - 1) + fib(n -2));
			}

			int main() {
				int n; cin >> n;
				for (int i = 0; i <= n; ++i) cout << fibb(i) << endl;
			}

	28. What is an ER Model?
	29. Difference between DBMS and RDBMS.
	30. Explain Entity and Attribute.

	31. What is a pointer?
		A pointer is a type of variable in C and C++, that can hold address of a type. They are generally used to hold addresses of other variables.

		Uses:-
			1. To access array elements.
			2. Used in data structures like Linked Lists, etc.
			3. Used to allocate and deallocate memory.
			4. Used to pass arguments by reference.

	32. Why do we use #include in C?
	33. Difference b/w pre-increment and post-increment.
		Pre-increment - used to increment variable by 1 before using its value.
		Post-increment - used to increment variable value by 1 after using its value.

	34. How much do you rate yourself in languages?

	35. Tell me something that is not in your resume.
		Tell the interviewer that you created a programming language all by yourself in class 12th as a challenge by a friend.

	36. How is Electronics and Communication related.
		Electronics is the backbone of Communications in today's world. One can communicate without using electricity, but within a short-range. Electronic devices increase the range of communication. Because of it, we can talk to someone far away from us.

	37. What is a signal? Types of Signals.
		A signal is the fundamental quantity that represents an information that is to be transmitted or recieved. It is a function that conveys some information.

		There are two types of signals:-
			1. Analog
				- Defined with respect to time
				- Can be defined by a continuous variable
				- Usually represented with sin or cos waves

			2. Digital
				- Can be represented with Discrete variables
				- Only hold two types of values, 0 and 1 and hence easy to analyse.
				- Sampling is done to replicate an analog signal

	38. Do Python/C/C++-based interview questions.
	39. Do ECE-based interview questions.
	40. Do OOPS-based questions.

	41. Be thorough with OpenCV and Face-Recognition.
	42. What are the data-types supported in Python?
		- Python has five standard data types:
			1. Numbers
			2. Strings
			3. Lists
			4. Tuples
			5. Dictionaries

	43. What is the difference b/w a list and a tuple?
		- Lists are mutable objects, which means that they can be modified at any point of the progam.

		- Tuples are non-mutable objects. Once declared, they cannot be changed. Tuples tend to be a bit faster than lists.

	44. How is memory managed in Python?
	45. C++ Memory Management?
	46. Explain Inheritance in Python.
		- Classes in Python have the ability to inherit properties of other languages - this is known as inheritance. Inheritance provides features like:-
			- Code Reusability. 
			- Time and efforts saved.
			- Improves program readability.
			- Ability to model real-world relationships b/w objects.

		- Following are supported in Python:-
			1. Single Inheritance:
				- When a class inherits only one superclass.
			2. Multiple Inheritance:
				- When a class inherits multiple superclasses.
			3. Multilevel Inheritance
				- When a class inherits a superclass and then another class inherits this derived class.
			4. Hierarchical Inheritance
				- When one superclass is derived by multiple subclasses.

	47. What is dictionary in Python.
		- A dictionary is a supported datatype in PYthon. It is a collection of unordered elements which are stored as key-value pairs, similar to a hash-map.

	48. Write code to count number of Capital letters in a file.
		fh = open('file.txt', 'r')
		c = 0
		for char in fh.read():
			if char.isupper():
				c += 1
		print(c)

	49. Why are negative indexes and why are they used?
		- Python supports negative indexing of arrays, which is not available in most of the programming languages. The last element being -1, the second last being -2 and so on.

	50. What is Software Development Life Cycle? What are it's types?

		- A process used by the software industry to design, develop and test professional/industry software.
		- It is followed by all professional software companies.

		Stages:-

			1. Planning and Requirement Analysis
			2. Defining Requirements
			3. Designing the Product Architecture
			4. Building or Developing the Product
			5. Testing the Product
			6. Deployment in the Market and Maintenance

		- Models:
			1. Waterfall Model
			2. Agile
			3. DevOps

	51. Use of Volatile keyword.
		- It is a qualifier applied to a variable when used. It is used to tell the compiler that the variable value may change at any time.

		- It is intended to prevent the compiler from applying any optimizations on objects that can change in ways that cannot be determined by the compiler.


	-> Any questions for the interviewer?

HR Round:-

	1. Tell me about yourself.
		Sir, I am Suraj Khati, I'm a final year student of B. Tech majoring in Electronics and Communication Engineering. Besides, programming and coding, my interests lie in Digital Art and Design, and videogames.

	2. Tell me about your family background.
		My family is almost a government-service based family. My grandfather was in the BSF, my father in the Army, my maternal grandfather was in the NHPC. Although the female side of my family are housewives. I am the only one who wants to get into the Corporate world. My sister is in class 7th.

	3. Why Capgemini/DXC/company?
		Sir, when I attended the pre-placement talk, I came to know about DXC Technology. It is a B2B company, formed recently in 2017. It was formed as a result of the merging of Computer Science Corporation and HPE Enterprises Division. I think the company name itself resonated with my beliefs as DXC means "Delivering eXcellence for our Customers". And in whatever I do, sir, I try to be perfect.

	4. DXC/Capgemini/company competitors?
		Other service-based companies like:
			1. Cognizant
			2. Infosys
			3. Capgemini
			4. Wipro
			5. Accenture

	5. ECE field companies? Why not join them?
		Sir, even though my branch in ECE. I started programming since class 11th, so programming has almost always been my passion. I chose ECE because I wanted to learn how computers worked on the physical level, as almost all software-based things, I can learn online for free.

		I want to work in the software-domain because I am passionate about programming and want to grow in this field.

	6. What did you do during lockdown to enhance your knowledge?
		During lockdown, sir, I did a few courses from Coursera. Also, with my CSE friend, I started a bit of Competitive Programming, so that I could improve my logical programming skills.

	7. Real life implementation/examples of Data Structures?
		Arrays:
			1. Storing player scores during a game. It can be sorted in descending order to show the highest score.

			2. A whole answer sheet can be stored in an array, the 0th index being the first question. The values can range from 1 to 4. And marks can be calculated by simply traversing the array.

			3. 2D-Arrays can be used to store bitmap images if hex-values are used to represent colors.

		Linked List:
			1. Previous and Next pages in a web browser can be browsed as the links can be stored in a Linked List.

			2. Can be used as a simple grocery list.

			3. In Operating Systems, the scheduler can internally use Linked Lists to prioritise processes accordint to urgency.

		Stacks:
			LIFO

			1. In real life, we see stacks being a stack of notebooks or plates, where to get to the last one, we will have to remove all the ones above it.

			2. In a parking lot, where the parking space is only one car wide, the last car will have to come out first to get to the last.

			3. In CS, stacks are used to store the Program Counter + 1 before calling a subroutine or a function. It will come back to the program after finishing the function.

			4. Used to implement Undo/Redo.

		Queues:
			FIFO

			1. A ticket line.
			2. A printer queue.
			3. A Phone-answering system, where calls are put on hold until one finishes.

		Circular Linked List:
			1. Useful in applications that repeatedly move around a list. For example, an OS may execute the instruction of one program, then move to the next, then the next, and back to the first program. It happens so fast that it gives an illusion of multi-tasking.

		Trees:
			1. Can be used to store hierarchical information -> example a file systems.
			2. HTML parsing tags form a hierarchy.


	8. Is Python better than C++? Which one do you prefer?
		
		Python being a fairly easy language to use, has it's use in many fields. It can even be taught to children. But sir, I think Python and C++ have their own scenarios, in which one might be preferrable than the other.

		For example, in C++, even a "Hello, World" code can take upto 5-6 lines. Whereas, in Python, a simple print statement will do. It makes prototyping easier.

		But on the other hand, C++ is used where speed is critical, such as in System Software, Operating Systems, and fast-paced Videogames.

	9. Tell me about your academics and if you have any backlog.

		I have been an above-average student almost throughout my academic life, although I did have my highs at times. In class 10th, I scored 9 CGPA, almost the highest in my class.

		In class 12th, sir, I spent all of my time learning to program in C++, as I had Biology for almost a month, and I lagged behind my classmates. Then I got interested in programming and made my own programming language.

		Throughout college life, I always mainted a CGPA above 7. And the total CGPA I have till 6th semester in 81.6%.

	10. In which technology are you good at?

		Sir, I am not good at any particular technology, as my interesets lie in core programming, building the logic of a program. But I am very much interested to learn about Facial Recognition, Computer Vision and Operating Systems Development.

	12. Will you relocate in the future?
		Answer yes.

	13. What are your strengths and weakness?
		
		Strengths:-
			1. I am a quick-learner -> give example of how I learned programming after Biology.
			2. I try and learn from my past mistakes -> since I scored badly in 12th, I was determined to improve my score during my B. Tech.
			3. I am an honest person, sir.
			4. I also have good concentration and focus -> can sit for an entire day to study for an exam.
			5. I try and emply creativity in almost everything I do, be it making a report or a PPT.

		Weaknesses:-
			1. I am quite an emotional person, can get affected by the smallest of things, but I am trying to work on it by doing meditation.

			2. I have a fear of speaking publicly. Other than anything, it is the one thing that scares me a lot.

			3. I sometimes overthink a lot and creates scenarios in my head which would hardly happen in real life.

	14. What is your dream job?
		My dream job is to be an engineer only, sir. I could not be happier doing anything other than building things I love and getting paid for it.

	15. Do you have a passport?
		No.

	16. Why should we hire you?

		I believe that I align with the company philosophy and would be a good addition to the company. I have the required skills to learn and grow in the job. I will put the company first and will prove my mettle.
