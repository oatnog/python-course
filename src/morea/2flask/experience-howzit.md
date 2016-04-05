---
title: "Howzit Web"
published: true
morea_id: howzitweb
morea_type: experience
morea_summary: "Adding more to our program"
morea_sort_order: 4
---

### "Hello World" on the Web

An experiential learning opportunity.  Here's our simple Flask web application with the addition of some lists:

{% highlight python linenos %}

from flask import Flask
import random

app = Flask(__name__)

greets = ["Hello", "Hi", "Howzit", "Greetings", "Aloha", "Sup"]
places = ["island", "state", "world", "solar system", "galaxy"]

@app.route('/hello')
def hello():
  greeting = random.choice(greets) + ", " + random.choice(places)
  return greeting + "\n"

if __name__ == '__main__':
  app.run()


{% endhighlight %}

### Adding HTML and CSS

It's time for our webapp to produce more than just words--it's time for real web pages.

To do this, we will use a template.

A Jinja2 template looks just like regular HTML, with the addition of double curly braces ("handlebar mustaches")

{% gist 208ee509e2fa6b39b401f27a8094143f %}

To use this template, we need to change our Python code a little. 

We'll *import* and use a new part of Flask called *render_template*. 

Note how the variable names "greet" and "place" match in the program and in the template.

{% highlight python linenos %}
from flask import Flask, render_template
import random

app = Flask(__name__)

greets = ["Hello", "Hi", "Howzit", "Greetings", "Aloha", "Sup"]
places = ["island", "state", "world", "solar system", "galaxy"]

@app.route('/hello')
def hello():
  return render_template("greeting.html",
    greet=random.choice(greets), place=random.choice(places))

#  greeting = random.choice(greets) + ", " + random.choice(places)
#  return greeting + "\n"

if __name__ == '__main__':
  app.run()

{% endhighlight %}