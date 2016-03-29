---
title: "Howzit Web"
published: true
morea_id: howzitweb
morea_type: experience
morea_summary: "Adding more to our program"
morea_sort_order: 4
---

### "Hello World" on the Web

An experiential learning opportunity.  Here's the simplest Flask web application:

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

A Jinja2 template looks just like regular HTML, with the addition of 

{% highlight html linenos %}
<!doctype html>
<html>
<head>
  <title>Greetings!</title>
  <style type="text/css">
    body {
      max-width: 600px;
      font-family: 'Courier New', Courier, monospace;
      margin: 1em auto;
    }
  </style>
</head>
<body>
  <h1>I am Greet-O-Tron. I have prepared for you this greeting.</h1>
  <p> {% raw %} {{ greet }}, {{ place }} {% endraw %} </p>
</body>
</html>
{% endhighlight %}

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