---
title: "Hello Web"
published: true
morea_id: helloweb
morea_type: experience
morea_summary: "Our first simple web application using Flask"
morea_start_date: "2015-06-11T18:00"
morea_sort_order: 3
---

### "Hello World" on the Web

An experiential learning opportunity.  Here's the simplest Flask web application:

{% highlight python linenos %}

from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"

if __name__ == "__main__":
    app.run()


{% endhighlight %}

PythonAnywhere will create this outline for you. Try it now.
Go to the "Web" tab in your dashboard, and click "Add a new web app"


### Hello, yourname

Add another *route*, or URL the webapp recognizes.

{% highlight python linenos %}
@app.route('/<name>')
def hello_name(name):
    return 'Hello, ' + name
{% endhighlight %}

### Debugging

If you run into problems, you can check the log, or
add this line to your program before app.run().

{% highlight python %}
app.debug = "TRUE"
{% endhighlight %}

This will enable the web-based debugger, where you can check what line of code caused the problem and what state the program was in when it died.