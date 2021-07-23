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

## Run Flask App
```
flask run
```