#HOW TO ENSURE THE QUALITY OF A SOFTWARE SYSTEM
	Due to the language barrier of working on the DianDian Project, my examples will have the social network "Facebook" as the target system.
	
My document will treat every testing solution that can be used to ensure the quality of the software system. Every solution will be described, explained and come with a concrete example applied on Facebook.

#1 Different kind of tests

One of the fondamental concept of software development is the preoccupation separation. It's a principle to respect when writing tests : A test must answer a problematic, it has to know the scope of the tested system and which abstraction level. All of those pieces of information must be written in the testing documentation.

Here are the different kind of tests.


###1.1 "White Box" and "Black Box" tests

"White Box" and "Black Box" tests are differenciated by the visibility the test developer have on the tested code.

**"White Box Test" :** The tester, to write his code take care of the internal structure of the implementation code. With this knoweledge he can easily observe the different branches and the cases that can provocated bugs and errors. Eventually the test can call private and protected methods.



**"Black Box Test" :** The tester doesn't take in consideration the code itself, he only tests the public part of the tested element.

*Example : If we want to test the photo upload on Facebook on white boxes we will see what is the tolerance of allowed type of files and maximum size whereas on black boxes we will do blind tests and will just see if it works or not.*



###1.2 Functionnal and non functionnal tests

**"Functionnal tests :"** We speak about functionnal test when a class success to fulfill the fixed objective by a given use case. It answers the questions "Does this code made THIS possible ?" or "Does this functionnality works ?"

**"Non functionnal tests" :** They are verificating properties which are not directly used by the code. It is to verificate the security or the capicity to handle many requests. It answers the question "Does this class can handle 1000 threads at the same time ?"

*Example : If we want to try the messenging part of Facebook, in a functionnal approach we will check if I send a message does it works ? Whereas in a non functionnal approach we will try to send tons of messages and how the server reacts to this.*



###1.3 Unit tests, integrated tests and system tests

While a unit test target to test an isolated unit during the test, an integration test is a test that link together different unit/components to verify that they work fine together. System testing would be considered as a global integrated test which verify the totality of the assembled system.



#2 Isolation

It is important for a test to test only one thing. Every class must have its tests and they only manipulate the tested class. If a test fails we should exactly know where it comes from and can easily find the programmation error.

*Example : If we want to test that a user has correctly been created we will put the creation inside our test method. Why ? Because if we create one test to create the user and another to check if that user exist how can we be sure the tests were executed in the right order ? And every test has to be independent*


#3 Determinism

A test is useful if we can test it again. If a test detects a defect and we correct it we need to be able to test it again to be sure the bug was removed. 

That's why it is necessary to provide systematically to the system the same datas. Avoid random values or store it to be able to test the same again. 

*Example : We are testing the security on the comment part and see if an SQL injection is possible. If we write special characters manually and check every possibilities, we can know what cause problems. If we start a test with randomly generated characters and brute force the form, if we see that it fails how can we know what caused the bug ?*


