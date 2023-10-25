# Flask-API-installation-

1.Install python 3.12.0 version

2.python -m pip install flask

3.In VS Code, create a new file in your project folder named app.py

4.import Flask and create an instance of the Flask object.
from flask import Flask
app = Flask(__name__)

5.use Flask's app.route decorator to map the URL route

@app.route("/")
def home():
    return "Hello world!"
6.Save the app.py file

7.In the Integrated Terminal, run the app by entering python -m flask run, which runs the Flask development server

8.To open your default browser to the rendered page, Ctrl+click the http://127.0.0.1:5000/ URL in the terminal

Hello world!

9.return Hello world! When accessed

if __name__ == '__main__':
    app.run()

10.Import from MySQL to html 

from flask import Flask, render_template
import mysql.connector

app = Flask(__name__)

# Configure your MySQL connection
db = mysql.connector.connect(
    host="localhost",
    user="root",
    password="Deepika@2001",
    database="users"
)

@app.route('/users')
def users():
    cursor = db.cursor(dictionary=True)
    cursor.execute("SELECT * FROM users")
    user_data = cursor.fetchall()
    cursor.close()
    return render_template('users.html', users=user_data)

if __name__ == '__main__':
    app.run()
