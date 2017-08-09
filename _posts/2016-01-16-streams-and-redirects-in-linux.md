---
layout: post
title: "Streams and Redirects in Linux"
description: ""
category: 
tags: [Linux, Article]
---
**Streams** and **Redirection** are words that come across a Linux user quite frequently. Both words seem quite trivial if you know about them but somewhat alien before you do (atleast to me). So let's change their interpretetion from alien to trivial.

What a stream is?
-----------------

The **shell** passes messages to **kernel** from the user and vice versa. These messages are nothing but a sequence of characters. Shell programmers use the word **stream** for this. So basically, **stream** == **sequence of characters**, but is usually associated with text flowing to and fro from the shell.

These streams can be of different kinds, and commonly known as:

1. **Input Stream (STDIN)** -> Sequence that you give to the shell. Like a command you enter, or some input to a program.
2. **Output Stream (STDOUT)** -> Sequence that the shell returns from a file or a process and displayed on the screen unless redirected.
3. **Standard Error Stream (STDERR)** -> STDERR is used to output error messages from failed processes. Kind of like STDOUT but for errors. This stream is treated differently than STDOUT, so STDOUT redirects won't work with this.

I/O Redirection
---------------

### Redirecting STDOUT

Assuming a *content* directory in *home* directory.

	$ ls content > output.txt

*ls* command, if completed successfully, displays the directory's contents by sending the output to the STDOUT stream. The STDOUT stream by default displays the output on the output device, like your monitor. What **>** operator does is redirect the STDOUT stream to a file, in this case *output.txt*. 

### Redirecting STDIN

Some programs require some input from the STDIN to continue. The **sort** utility is one such example. To redirect STDIN to take input from a file rather than an input device (which it uses by default like keyboard), **<** operator is needed.

	$ sort < input.txt

*input.txt* contains some random numbers. **sort** would output the sorted sequence on the STDOUT (by default, your screen). 

### Redirecting both STDIN and STDOUT

Just combine both redirect operators and BOOM!

	$ sort < input.txt > output.txt

One can guess the result.

### Redirecting STDERR

As written above, STDERR is similar to STDOUT (as output to this stream is displayed on the screen by default). Assuming there is no directory named *content2* in home.

	$ ls content2 > output.txt

There would be an error message displayed on the screen. If you're thinking why the message didn't got written to the file? -> STDOUT redirects won't work with STDERR. The error message from *ls* or any other program is usually sent to STDERR. To redirect STDERR to a file:
	
	$ ls content2 > output.txt 2> error.txt

**2>** is the operator for STDERR redirection. In the command above, any successful output would be sent to *output.txt* and any error message would be sent to *error.txt*.

### &gt; or &gt;&gt;

I/O can be redirected using these two operators. The first one i.e **>** would create a new file and send the output to that one.
	
	$ ls > output.txt

*output.txt* would be created no matter what. If there is already an *output.txt* file, all previous content would be removed.

The second operator i.e **>>** would append rather than clear previous content. If there isn't a file at all, a new file would be created else, the output would be appended to the previous one. 

Summary
-------

* Three kind of streams: stdin, stdout and stderr. 
* stderr similar to stdout, but for errors.
* &gt; operator to redirect stdout, 2> operator to redirect stderr.
* < operator to redirect stdin.
* &gt;&gt; operator to append the content.
