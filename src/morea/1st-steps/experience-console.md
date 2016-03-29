---
title: "Python Console exploration"
published: true
morea_id: console
morea_type: experience
morea_summary: "Print, use variables, and input on the Console"
morea_sort_order: 2
---

### Hello World

This is the traditional first program people run in a new language.

From your PythonAnywhere Dashboard, start a Python 3.4 console.

{% highlight python %}
print("Hello, World")
{% endhighlight %}

Type this in, then press enter.

print() is a **function**. It does something using "Hello, World".

### Variables

Variables are like labels, letting you refer to something by a different name.

{% highlight python %}
myname = "Allan"
print("Hello, " + myname)
{% endhighlight %}

Variables can be operated on, just like you'd expect.

{% highlight python %}
x = 2
y = 4
z = x + y
{% endhighlight %}

In the console, just type a variable to see what it contains.

### Input

Use the input() function to read in what a user types and store it under a variable.

{% highlight python %}
name = input("What's your name? ")
print("Hello, " + name)
{% endhighlight %}

### Lists and Loops

If you are familiar with Scratch or the Code.org tutorials, you will know about loops.

Instead of looping for a certain number of times, it is more common in Python to loop over each entry in a list (or another iterator).

 - Note the extra spaces after the "for" line! They are essential. Everything after that space gets included in the loop.

{% highlight python %}
>>> numbers = [1,2,3]
>>> print(numbers)
[1, 2, 3]
>>> for number in numbers:
...     print(number)
... 
1
2
3
>>> 
{% endhighlight %}
