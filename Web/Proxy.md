## 1\. Proxies

Proxies are intermediary servers that stand between clients and other servers. They play a critical role in enhancing performance, security, and reliability in various network scenarios.

## 1.1 Forward Proxy

A forward proxy is a server that acts on behalf of clients to make requests to other servers. Forward proxies can be used for various purposes, such as providing anonymity, enforcing security policies, and caching content.

## 1.2 Reverse Proxy

A reverse proxy is a server that handles client requests on behalf of other servers. Reverse proxies can provide load balancing, SSL termination, and content caching, among other benefits.

![](https://miro.medium.com/v2/resize:fit:700/1*oeUPfO992X54Q15f39Nsig.png)

Forward Proxy vs Reverse Proxy





**A. Singleton**  
A creational design pattern that ensures a class has only one instance and provides a global point of access to it.

![](https://miro.medium.com/v2/resize:fit:700/1*5Jzyklw4wS3NJEMG5oZ55g.png)

Singleton Pattern

```python
class Singleton:  
    _instance = None  
        def __new__(cls):  
        if cls._instance is None:  
            cls._instance = super().__new__(cls)  
        return cls._instance  
  
singleton1 = Singleton()  
singleton2 = Singleton()  
print(singleton1 is singleton2)  # Output: True
```

**B. Factory Method**  
A creational design pattern that provides an interface for creating objects in a superclass, allowing subclasses to alter the type of objects that will be made.

![](https://miro.medium.com/v2/resize:fit:700/1*cnw38-WAYmtzp8ldD_nPOg.png)

Factory Pattern

```python
from abc import ABC, abstractmethod  
class Creator(ABC):  
    @abstractmethod  
    def factory_method(self):  
        pass  
class ConcreteCreator(Creator):  
    def factory_method(self):  
        return ConcreteProduct()  
class Product(ABC):  
    @abstractmethod  
    def operation(self):  
        pass  
class ConcreteProduct(Product):  
    def operation(self):  
        return "ConcreteProduct"  
creator = ConcreteCreator()  
product = creator.factory_method()  
print(product.operation())  # Output: ConcreteProduct

```

**C. Observer**  
A behavioural design pattern that allows objects to notify other things about changes in their state without being tightly coupled.

![](https://miro.medium.com/v2/resize:fit:700/1*rNVuvNt78ORclHLQaEIySw.png)

Observer pattern

Simple observer pattern implementation in Python

```python
from abc import ABC, abstractmethod  
class Subject(ABC):  
    def __init__(self):  
        self._observers = []  
    def attach(self, observer):  
        self._observers.append(observer)  
    def detach(self, observer):  
        self._observers.remove(observer)  
    def notify(self):  
        for observer in self._observers:  
            observer.update(self)  
  
class ConcreteSubject(Subject):  
    _state = None  
    @property  
    def state(self):  
        return self._state  
    @state.setter  
    def state(self, value):  
        self._state = value  
        self.notify()  
  
class Observer(ABC):  
    @abstractmethod  
    def update(self, subject):  
        pass  
  
class ConcreteObserver(Observer):  
    def update(self, subject):  
        print(f"ConcreteObserver: {subject.state}")  
  
subject = ConcreteSubject()  
observer = ConcreteObserver()  
subject.attach(observer)  
  
subject.state = "New State"  # Output: ConcreteObserver: New State

```




