Compiler-final-project
======================

NCU-Compiler-final-project


Compiler Final Project

In this final project, we give you an incomplete mini-pascal compiler (mpc) with incomplete source code. The files of this project are put in your home directory in your account. The provided source code, although with missing features, can still be compiled successfully. 
In your home directory, a complete mpc called “standard_mpc” is provided for your reference. You can run this program with some *.pas to test the results. If your implementation is correct, your program should behave the same as “standard_mpc”. 
HOWEVER, “standard_mpc” cannot generate x86 assembly code. If you manage to implement code generation, please verify your assembly code by simply running it.

Your tasks are to
1.	Read the language specifications about mini-pascal.
2.	Read the mini-pascal examples in the language specification documents.
3.	Test the *.pas with standard_mpc 
4.	Trace the parse.y with the YACC knowledge you learned from the lab classes.
5.	The parse.y of mpc basically is to build an AST tree when parsing is done. So, you need to understand how it is done by tracing 
    	Read the %union section in parse.y. This is where an AST node is defined.
    	In %union, there are many typedefs. Trace “structs.h” for your interested typedefs.
    	Read the AST building node function defined in astree.h/astree.c
6.	Once you have understood the AST data structure in mpc. It is a good exercise to trace main() in mpc.c. A very good entry point      is from print_ast() in mpc.c at line starting from 110. This procedure visits the AST tree as told in the classes. It is crucial     to understand print_ast() if you want to complete this project.
7.	While tracing the code, you can see a lot of places in the code (parse.y or *.c) are gone and replaced by a comment. These are       the places you should complete one by one.
8.	The lexical analyzer of mini-pascal compiler (mpc) is implemented in c language (scan.h / scan.c), so you will not find *.l file     in mpc.

The yacc parser of mini-pascal compiler (mpc) is implemented in parse.y. To execute commands sequentially, we can write a shell script or Makefile. We have installed make tool and put the Makefile in your project directory, so you don't have to write a shell script to compile mpc.

	How to use make?

(Compile the mpc project, it will output an executable "mpc" program)
  $ make

	(If you want to clean the output file)
  $ make clean

There are 10 features in parse.y you need to complete. We put 10 test cases in feature_test directory to let you test your implementation. If you implement it correctly, it should behave the same as standard_mpc.

	Running mpc compiler
We provide a mpc program called "standard_mpc" in your project directory. You can execute the program by: 

  $ ./standard_mpc

With no arguments, usage information is displayed. 
For example:
If you want to print the AST tree and save it into “feature1_correct.parse” , you can use “-p” option: (In mpc project directory)

  $ ./standard_mpc -p feature_test/feature1.pas feature1_correct.parse
  $ ./standard_mpc -p feature_test/feature1_block.pas feature1_correct.hi (會一次產生兩個)

Assume you have completed feature 1 and want to test your own mpc.
(In mpc project directory)

  $ ./mpc -p feature_test/feature1.pas feature1_me.parse

If you have done right, two feature1_correct.parse files should be the same.
feature1_correct.parse跟 feature1_me.parse 一樣

NOTE 1:
Using putty (or other ssh client) to connect our server and modify the source code in server.
If you feel tracing source code in our linux environment is not convenient, we also provide the source code files here to let you trace code easily.  

NOTE 2:
For more formal pascal grammar see:
http://www.tutorialspoint.com/pascal/pascal_overview.htm

NOTE 3:
You can trace the entry point of mpc in mpc.c and structures declaration in sturcts.h .

NOTE 4:
Make sure you must achieve these features according to the order in parse.y.


Project Grade

For features 1-10, complete one feature you can get 7 point and total grade in this part is 70. The rest of the 30 point is for feature 11 (code generation), we will judge the following 5 features:

Feature 11 code generation
Feature	Description	Points
feature2_vardecl	Generate NASM assembly for variable declaration.	6
feature3_arraytype	Generate NASM assembly for array type declaration.	6
feature7_ifstmt	Generate NASM assembly for if statement.	6
feature8_casestmt	Generate NASM assembly for case statement.	6
feature10_forstmt	Generate NASM assembly for for loop statement.	6

Feature tips’ location
parse.y 
  Line 94:            Feature 1
	Line 160:           Feature 2
	Line 207:           Feature 3
	Line 230:           Feature 3 (continue)
	Line 254:           Feature 4
	Line 279: 	        Feature 5 
	Line 334:           Feature 5 (continue)
	Line 439:           Feature 6
	Line 448:           Feature 6 (continue)
	Line 454:           Feature 6 (continue)
	Line 463:           Feature 7
	Line 479:           Feature 8
	Line 489:           Feature 8 (continue)
	Line 498:           Feature 8 (continue)
	Line 512:           Feature 8 (continue)
	Line 537:           Feature 9
	Line 548:           Feature 10
	Line 560: 		      Feature 11
