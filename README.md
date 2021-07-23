# Flask-Practice
For practice

> Definition credit for https://www.softwaretestinghelp.com/python-flask-tutorial/

> Flask is a web development framework with a built-in development server and a debugger. It is used for developing Web Applications in Python programming language.

> It integrates with other third-party services and APIs to bring richness and meaning to the application under development.


## Set up
```
pip install -r requirements.txt
```

## Basic Flask App (app.py)
```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def index():
    return "hello, world!"

if __name__ == "__main__":
    app.run()
```
arguments in ```app.run()```
```python
app.run(debug=True, host='0.0.0.0', port=3000)
    # 'debug=True' make it easier for debugging 
    #       every time you modify the code, it will reflect on the web browser
    #       dont need to stop the app and re-run it again
    # 'host='0.0.0.0'' for others to access the web on their machines
    #       by default, we are using 'localhost' which cant be accessed by other machines
    # 'post=3000' if port 5000 cant use (we can just change to another port)
```

## Import render_template
1. Make a directory called ```templates``` (the directory name should be exactly same)
2. Write an ```index.html``` inside ```templates``` directory
3. Inside ```app.py```, render file ```index.html``` such that we can format it nicely in other place (```index.html```)
```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
    title = 'Flask Web App'
    return render_template('index.html', title=title)

if __name__ == "__main__":
    app.run(debug=True, host='0.0.0.0', port=3000)
```
```html
<html>
    <head>
        <title>{{ title }}</title>
    </head>
    <body>
        <h1>Hello, World!</h1>
    </body>
</html>
```
## Run Flask App
```
flask run
```