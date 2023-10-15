Process
Instance of a program/application
Has resources such as memory, etc.
Has at least one thread


Thread
Sequence of programmed instructions
The thing that executes a program's code
Utilizes process resources

Each parent thread Can have up to 4 Child thread  running concurrently 
![[SmartSelect_20230528_214857_Pluralsight.jpg]]


Multithreading is used to run things in Parallel or Parallel Processing


```Java


class Adder (
private String inFile, outFile;
public Adder(String inFile, String outFile) {/* assign filenames to member fields */ }
public void doAdd() throws IOException (
int total = 0;
String line = null;
try (BufferedReader reader = Files.newBufferedReader(Paths.get(inFile))) {
while ((line = reader.readLine()) != null)
total += Integer.parseInt(inline);
}
try (BufferedWriter writer = Files.newBufferedWriter(Paths.get(outFile))) {
writer.write("Total: " + total);
		}
	}
}



```

![[SmartSelect_20230528_215953_Pluralsight.jpg]]

## single thread usage
![[SmartSelect_20230528_220051_Pluralsight.jpg]]

![[SmartSelect_20230528_220232_Pluralsight.jpg]]

![[SmartSelect_20230528_220334_Pluralsight.jpg]]

## Thread foundation type 

Runnable interface
- Represents a task to be run on a thread  
- only member is the run method
![[SmartSelect_20230528_221020_Pluralsight.jpg]]


Thread class
- Represented a thread of execution  
- Can interact with and effect thread state  
- Begin execution with start method

![[tempFileForShare_20230528-224532.jpg]]

![[tempFileForShare_20230528-224757.jpg]]

![[tempFileForShare_20230528-224859.jpg]]
```Java 

String[] inFiles = ("./file1.txt"
String[] outFiles = ("./file1.out.txt"
"./file6.txt");
./file6.out.txt");
Thread[] threads = new Thread[inFiles.length];
for(int i=0; i < inFiles.length; i++) (
Adder adder = new Adder(inFiles[i], outFiles[i]);
threads[i] = new Thread(adder);
threads[i].start();
for (Thread thread:threads)
thread.join(); // Blocks waiting for thread completion
```


![[SmartSelect_20230528_225140_Pluralsight.jpg]]

## Thread pool type  
  
  
ExecutorService interface  
- Models thread pool behavior 
- Can submit tasks  
- Request and wait for pool shutdown  
  
  
  
Executors class  
- Methods for creating thread pools
- Dynamically sized pools  
- Size limited pools  
- Pools that schedule tasks for later




![[SmartSelect_20230529_133524_Pluralsight.jpg]]

## Threading relationship Types 

### Callable interface
Represents a task to be run on a thread
Can return results
Can throw exceptions
Only member is the call method


### Future interface
Represents results a thread task
Returned by ExecutorService.submit
The key method is get
Blocks until task completes
Returns Callable interface result
Throws Callable interface exception