
## Samsung Interview - Computer Vision AI Team 
#### Questions related to AI  :
	 - CNN
	 - GAN 
 #### Questions related to programming  (mostly C++ ) :
		 - Inheritance : order of constructors & destructors  
		 - Virtual inheritance
		 - Pointers vs Reference vs Value
		 - Smart Pointers (unique_ptr, shared_ptr, aut_ptr...)
		 -  R Value
		 - Lambda functions ( how to call it and what the [] stands for)
		 - List vs Vectors ( memory layout)
		 - Singly vs Doubly Linked List
		 - Map VS Unordered Map ( hashmap how it works)
		 - Volatile variable
		 -  What is std::move ? 
		 -  Is c++ multithreaded and what does it mean ?
		 - Mutex
		 - Deadlock 
# Answers 
							 CNN answers :
 ###  What is a CNN ? 
 CNN’s are used to perform analysis on images and visuals. These classes of neural networks can input a multi-channel image and work on it easily with minimal preprocessing required.
 #### Why do we use convolutions for images rather than just FC layers? [[src](http://houseofbots.com/news-detail/2849-4-data-science-and-machine-learning-interview-questions)]

Firstly, convolutions preserve, encode, and actually use the spatial information from the image. If we used only FC layers we would have no relative spatial information. Secondly, Convolutional Neural Networks (CNNs) have a partially built-in translation in-variance, since each convolution kernel acts as it's own filter/feature detector.

#### [](https://github.com/andrewekhalel/MLQuestions#23-what-makes-cnns-translation-invariant-src)What makes CNNs translation invariant? [[src](http://houseofbots.com/news-detail/2849-4-data-science-and-machine-learning-interview-questions)]

As explained above, each convolution kernel acts as it's own filter/feature detector. So let's say you're doing object detection, it doesn't matter where in the image the object is since we're going to apply the convolution in a sliding window fashion across the entire image anyways.

### GAN 
#### What does GAN do? 
The main focus for GAN (Generative Adversarial Networks) is to generate data from scratch, mostly images but other domains including music have been done
#### What are the components of GAN? [[src](https://intellipaat.com/interview-question/artificial-intelligence-interview-questions/)]
-   Generator
-   Discriminator	
	
							C++ coding answers
	
### Inheritance : order of constructors & destructors  in C++
Order of constructor call for Multiple Inheritance
For multiple inheritance order of constructor call is, the base class’s constructors are called in the order of inheritance and then the derived class’s constructor.

![enter image description here](https://media.geeksforgeeks.org/wp-content/uploads/order-of-constructor.png)
	 
-   Whenever the derived class’s default constructor is called, the base class’s default constructor is called automatically.
-   To call the parameterized constructor of base class inside the parameterized constructor of sub class, we have to mention it explicitly.
-   The parameterized constructor of base class cannot be called in default constructor of sub class, it should be called in the parameterized constructor of sub class.

[**Destructors**](https://www.geeksforgeeks.org/destructors-c/)  in C++ are called in the opposite order of that of Constructors.

###  Virtual inheritance
-  The diamond problem

_Virtual inheritance_  is a C++ technique that ensures that only one copy of a base class’s member variables are inherited by second-level derivatives (a.k.a. grandchild derived classes). Without virtual inheritance, if two classes B and C inherit from class A, and class D inherits from both B and C, then D will contain two copies of A’s member variables: one via B, and one via C. These will be accessible independently, using scope resolution.

Instead, if classes B and C inherit virtually from class A, then objects of class D will contain only one set of the member variables from class A.

As you probably guessed, this technique is useful when you have to deal with multiple inheritance and it’s a way to solve the infamous diamond inheritance.
![enter image description here](https://www.sandordargo.com/assets/img/diamon-inheritance.png)		 
		
###  Pointers vc Reference vs Value
The main differences between pointers and references are -

-   References are used to refer an existing variable in another name whereas pointers are used to store address of variable.
    
-   References cannot have a null value assigned but pointer can.
    
-   A reference variable can be referenced by pass by value whereas a pointer can be referenced but pass by reference.
    
-   A reference must be initialized on declaration while it is not necessary in case of pointer.
    
-   A reference shares the same memory address with the original variable but also takes up some space on the stack whereas a pointer has its own memory address and size on the stack.

     Type *pointer;
    
	Type *pointer;
	pointer = variable name;
	
	Type &newname = existing name;
	
	Type &pointer;
	pointer = variable name;
	
###  Smart pointers
	-   auto_ptr
	-   unique_ptr
	-   shared_ptr
	-   weak_ptr
	
**Why is auto_ptr deprecated?**  
It takes ownership of the pointer in a way that no two pointers should contain the same object. Assignment transfers ownership and resets the rvalue auto pointer to a null pointer. Thus, they can’t be used within STL containers due to the aforementioned inability to be copied.
**When to use unique_ptr?**  
Use unique_ptr when you want to have single ownership(Exclusive) of the resource. Only one unique_ptr can point to one resource. Since there can be one unique_ptr for single resource its not possible to copy one unique_ptr to another.

**When to use shared_ptr?**  
Use shared_ptr if you want to share ownership of a resource. Many shared_ptr can point to a single resource. shared_ptr maintains reference count for this propose. when all shared_ptr’s pointing to resource goes out of scope the resource is destroyed.

**When to use weak_ptr?**  
When you do want to refer to your object from multiple places – for those references for which it’s ok to ignore and deallocate (so they’ll just note the object is gone when you try to dereference).

### L Value &  R Value
Put simply, an  _lvalue_  is an object reference and an  _rvalue_  is a value. 

An lvalue is an expression that yields an object reference, such as a variable name, an array subscript reference, a dereferenced pointer, or a function call that returns a reference. An lvalue always has a defined region of storage, so you can take its address.

An rvalue is an expression that is not an lvalue. Examples of rvalues include literals, the results of most operators, and function calls that return nonreferences. An rvalue does not necessarily have any storage associated with it.

    #define rvalue 42
	int lvalue;
	lvalue = rvalue;
. 
	
###  Lambda functions ( how to call it and what the [] stands for) 
\
    _[ capture clause ] (parameters) -> return-type_ 
_{_ 
 _definition of method_ 
_**}**_

A lambda expression can have more power than an ordinary function by having access to variables from the enclosing scope. We can capture external variables from enclosing scope by three ways :  
Capture by reference  
Capture by value  
Capture by both (mixed capture)  
Syntax used for capturing variables :  
[&] : capture all external variable by reference  
[=] : capture all external variable by value  
[a, &b] : capture a by value and b by reference  
A lambda with empty capture clause [ ] can access only those variable which are local to it.

    `sort(v.begin(), v.end(), [](``const` `int``& a,` `const` `int``& b) ->` `bool`
    `{` 
    `return` `a > b;
    `});`

    `auto` `pushinto = [&] (``int` `m)`
    `{`
    `v1.push_back(m);`
    `v2.push_back(m);`
    `};`
\\

###  List vs Vectors ( memory layout) 

List in C++ stores the elements at the non-contiguous memory location. It is considered a doubly linked list internally.

A vector in C++ stores the elements at the contiguous memory location. It is considered to be a type of dynamic array internally.

Insertion and deletion of elements in List at any position take constant time as it involves the use of pointers and their swapping.

Insertion and deletion of elements at the last take constant time but insertion and deletion elsewhere (in the starting or middle) takes a lot of time as the array needs to be traversed.

List does not have any fixed size or a default size as it is a doubly-linked list and can be resized upon insertion or deletion.

Vector is a dynamic array and has the default size.

Memory required to store the elements in the List is comparatively large as it holds the element as well as the pointers for the next and previous nodes.

Memory required to store the elements in the Vector is lesser than List as it uses memory for the element only.

Random access of elements in the List is not possible as it is implemented as the doubly linked list. Programmers need to access the elements by traversing through the pointers.

As the elements in Vector are stored sequentially like an array, so the elements can be accessed randomly by providing the index number only.

###  Singly vs Doubly Linked List
![enter image description here](https://diego-shared-files.s3.eu-west-2.amazonaws.com/linked-list.jpeg)

###  unorederd_map vs map  
When it comes to efficiency, there is a huge difference between maps and unordered maps.  
We must know the internal working of both to decide which one is to be used.
map. 

 - Ordering :  increasing order  / no order 
 - Implementation : BST / hash-table
 - Search Time :  log(n) / O(1) or O(n)
 -  Insertion Time : log(n) + rebalance / O(1) or O(n)
 - Deletion Time : log(n) + rebalance / O(1) or O(n)
 
https://www.geeksforgeeks.org/map-vs-unordered_map-c/

###  Volatile variable 
It is used to tell the compiler, that the value may change at any time.
For example : Modified by hardware

###  What is std::move ? 
he first thing to note is that `std::move()`  **doesn't actually move anything**. It changes an expression from being an [lvalue](http://en.cppreference.com/w/cpp/language/value_category) (such as a named variable) to being an [xvalue](http://en.cppreference.com/w/cpp/language/value_category). An xvalue tells the compiler: "You can plunder me, **move** anything I'm holding and use it elsewhere"

A typical use is 'moving' resources from one object to another instead of copying

 The move constructor is used instead of the copy constructor, if the object has type "rvalue-reference" (`Type &&`).

###  Is c++ multithreaded and what does it mean ?
_Multithreading is a specialized form of multitasking_ and a multitasking is the feature that allows your computer to run two or more programs concurrently.
C++ multithreading involves creating and using thread objects, seen as std::thread in code, to carry out delegated sub-tasks independently.

### What is mutex 
A Mutex is a **Mut**ually **ex**clusive flag. It acts as a gate keeper to a section of code allowing one thread in and blocking access to all others. This ensures that the code being controlled will only be hit by a single thread at a time. Just be sure to release the mutex when you are done. :)

###  What is a deadlock 
Deadlock is _a situation where a set of processes are blocked because each process is holding a resource and waiting for another resource_
![enter image description here](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2015/06/deadlock.png)
