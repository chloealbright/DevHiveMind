---
tags: 
author:
  - jacgit18
Status: init
Started: 
EditDate: 
Relates:
---
Python is a full-fledged, high-level, and object-oriented programming language. Since it’s been around for close to 30 years, it has a ton of libraries, APIs, and ancillary tools available. Python is conducive to several programming paradigms, and it’s extensively used for business applications. 

Its community, libraries, and supporting platforms are far reaching. Hence, it is an ideal programming language for most businesses that are required to develop applications for different and often uncorrelated use cases.


Python has issues with threads. It’s built on the Global Interpreter Lock, which does not allow it to operate several threads at once. This means that you cannot run another process before the sequentially historical process is over. 

Although Python is dynamically typed, it’s more of a drawback in terms of scaling. Larger teams can find it difficult to maintain code when the project scales. 

In stark contrast to Node.js, Python doesn’t provide such functionalities and doesn’t support multithreading. You have to run and finish one process before others can be called in. This makes Python a little stringent. 

Although there are some tools that can help you create asynchronous apps using Python, they don’t make Python inherently asynchronous. You would end up using workarounds in the project and not actually get the desired asynchronicity.  

Python’s innate architecture prohibits multithreading and is a problem in this aspect as well. It slows down the processing speed as processes don’t run parallelly. While Python’s syntax is easy to learn and execute, it is not fast enough for applications that frequently recall data from the web server.  

Python’s simpler syntax makes it apt for all forms of project except one – mobile apps. For IoT solutions and cloud apps, Python is being used more and more by a large number of programmers.  

Python’s simpler syntax and lack of parallel processes come in handy while scanning the code for bugs and errors.



The Jupyter Notebook is the original web application for creating and sharing computational documents. It offers a simple, streamlined, document-centric experience. 

PIP is a package manager for Python, which means it allows you to install and manage libraries and dependencies that are supplemental to the standard library. basically the npm of python    

venv is a module used to create and manage virtual environments is called venv . venv will usually install the most recent version of Python that you have available. If you have multiple versions of Python on your system, you can select a specific Python version by running python3 or whichever version you want.


![[_Images/Languages/GetImage (4).jpeg]]
## Data Science Topics  

Data Handling  

	○ Working with Data, Data Exploration and Visualization 

Machine Learning  

	○ Supervised Learning, Regression, Classification, Evaluation Metrics, Clustering, Data Reduction, Ensemble Methods  

Feature Engineering and Model Tuning  

Natural Language Processing  

Deep Neural Networks / Image Classification (CNN’s) 


Jupyter Lab 

Numpy/Pandas  

Sklearn  

Matplotlib & Seaborn  

Keras




In the context of Python programming, "Python" and "Python 3" refer to different versions of the Python programming language. Here are the key differences:  
  
1. **Python 2 vs. Python 3**: Python 2 and Python 3 are two major branches of the Python language. Python 2 was the older version and has been officially discontinued as of January 1, 2020. Python 3 is the current and actively maintained version of Python.  
  
2. **Syntax Differences**: Python 3 introduced several syntax changes and improvements over Python 2. Some of the key differences include changes to the `print` statement (it's now a function in Python 3), integer division ( `/` performs true division in Python 3), and how strings are handled (Python 3 uses Unicode strings by default).  
  
3. **Compatibility**: Code written in Python 2 is not directly compatible with Python 3 due to the syntax changes. Therefore, if you have Python 2 code, you'll need to make modifications to run it in Python 3.  
  
4. **Library and Ecosystem**: Over time, many Python libraries and packages have been updated to be compatible with Python 3. However, some older libraries may still be primarily Python 2 compatible. It's important to ensure that the libraries you intend to use are compatible with your chosen Python version.  
  
5. **Community Support**: The Python community and the Python Software Foundation strongly encourage developers to use Python 3. As Python 2 is no longer maintained, security updates and new features are only added to Python 3.  
  
In summary, "Python" generally refers to Python 3, which is the current and recommended version of the language. Python 2 is outdated and no longer maintained, so it's best to use Python 3 for all new projects and to migrate existing Python 2 code to Python 3 to ensure compatibility and ongoing support.