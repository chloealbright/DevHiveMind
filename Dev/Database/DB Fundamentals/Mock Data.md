if using mock data and adding you need to check fixture if previous data exist if it does it needs to be flushed within fixture method  

If db table not changing like roles table don't need to create fixtures for it 

Mocking is primarily used in unit testing. An object under test may have dependencies on other (complex) objects. To isolate the behaviour of the object you want to test you replace the other objects by mocks that simulate the behaviour of the real objects. This is useful if the real objects are impractical to incorporate into the unit test. 

In short, mocking is creating objects that simulate the behaviour of real objects. 

  

At times you may want to distinguish between mocking as opposed to stubbing. There may be some disagreement about this subject but my definition of a stub is a "minimal" simulated object. The stub implements just enough behaviour to allow the object under test to execute the test. 

A mock is like a stub but the test will also verify that the object under test calls the mock as expected. Part of the test is verifying that the mock was used correctly. 

To give an example: You can stub a database by implementing a simple in-memory structure for storing records. The object under test can then read and write records to the database stub to allow it to execute the test. This could test some behaviour of the object not related to the database and the database stub would be included just to let the test run. 

If you instead want to verify that the object under test writes some specific data to the database you will have to mock the database. Your test would then incorporate assertions about what was written to the database mock. 

[https://blog.scottlogic.com/2016/02/08/data-mocking.html](https://blog.scottlogic.com/2016/02/08/data-mocking.html)





This is a good answer, but it unnecessarily restricts the concept of mocking to objects. Replacing "object" with "unit" would make it more general. 

I do understand the difference of stub vs. mock. Only thing is that if you're testing your cases with a stub and it passes then can't you conclude that you're already using the stub hence you no longer need the verification?  

Coming back to answer my own question above. The answer, is that the only way to validate that the code went through the desired function and not another function is using a bool check. Using that bool check is the distinction between stubs and mocks. Having that said a lot of times you literally just test the a function's output, so a mock doesn't apply in this case.

