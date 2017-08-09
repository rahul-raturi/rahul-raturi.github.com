---
layout: post
title: "Lvalues and Rvalues in C"
description: ""
category: 
tags: [C, Article]
---
Outline
-------
The terms *lvalue* and *rvalue* are generally associated with compiling errors. This error is not uncommon when compiling a C program.

	error: lvalue required as left operand of assignment.

I'll be describing *lvalues* and *rvalues* in C. Though, there are some subtle difference in meaning and definition of these terms across various standards and also between C and C++, but the basic idea is same.

Definition
----------
Basically, any object in C that occupies some space in memory (i.e. has some address), is an *lvalue*. We can see and/or modify the contents at that location. The rest of the expressions are *rvalues*.

### Some Examples

#### First example 

	int a=10;	//a is an lvalue
	int b;		//b is an lvalue
	10=b;		//Error: lvalue required at left

Here, **a** is an *lvalue* as it refers to an identifiable memory location. As **10** doesn't qualifies as an lvalue (hence it's an *rvalue*), we can't assign it a value. It makes no sense to ask a number to store a value which itself doesn't have a fixed address in memory.

#### Second example

	int fun() {
		return 10;
	}
	int main() {
		fun() = 11; //Error: lvalue required at left
		return 0;
	}

Same thing here. First the function gets called and generates value **10** which is an *rvalue*, so compiler generates the error.

In C++ it is possible to execute the above code as C++ supports functions returning reference. For example:

	int a=10;
	int& fun() {
		return a;
	}
	int main() {
		fun()=11;
		return 0;
	}

The code above will execute just fine, and update the value of **a** to 11.

Note: I've declared **a** as global because one can't return a reference to a local value as local variables get destroyed as function's execution completes.

#### Third example

An expression isn't an *lvalue* either. It doesn't have an memory location associated with itself.

	int a=10;
	a+1 = 11;	//Error: lvalue required at left

The compiler first computes **a+1**, which doesn't results in an *lvalue*, hence compiler complains.

### Some interconversions

There are often times when a conversion is required between *lvalue* and *rvalue* for an expression. For example,
	
	int a=10;
	int b=11;
	int c=a+b;	//'+' requires two rvalues to operate

As "+" requires *rvalues*, and **a** and **b** are *lvalues*, an implicit conversion is performed by the compiler. So, generally speaking, the compiler first extracts values of **a** and **b**, passes them to "+", and then fetches the result.

In the example above, an *lvalue* is converted to an *rvalue*. In some cases, an *rvalue* is converted to an *lvalue*. In case of unary **\***, such conversion happens.

	int *p = &ofSomeArray;
	*(p+1) = 10;	//Here 'p+1' is an rvalue

The expression "\*p+1" (which is an *rvalue*) is converted to an *lvalue* by operator **\***.

### Finishing off

As a general definition, *lvalues* are objects in C (an integer variable, structure etc), to which we can assign some values. If you can't assign a value to it, the expression is an *rvalue*. Although, this definition is not precise. For example, a *const* variable is an *lvalue* but you can't assign it any value post initialization. But, the definition above works fine for most of cases and is easier to understand(and recall) too.

If you find any error in this article or have a suggestion, please post a comment.
