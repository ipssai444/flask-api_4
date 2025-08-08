Flask To-Do REST API

A simple REST API built using Flask to manage a to-do list. Supports CRUD operations: Create, Read, Update, Delete. Data is stored in Python in-memory structures (list, dict), making it easy for beginners.

Features:
- GET /tasks      Retrieve all tasks.
- POST /tasks     Add a new task.
- PUT /tasks/{id} Update an existing task by ID.
- DELETE /tasks/{id} Delete a task by ID.

Tech Stack:
Python 3.x, Flask

Installation & Setup:
Clone the repository:
git clone https://github.com/ipssai444/flask-api_4.git
cd flask-api_4

Create & activate a virtual environment:
On Windows (PowerShell):
python -m venv flask-api
flask-api\Scripts\activate

On Mac/Linux (bash):
python3 -m venv flask-api
source flask-api/bin/activate

Install dependencies:
pip install flask

Run the API:
python app.py

The API will be available at http://127.0.0.1:5000

API Usage Examples:

To GET all tasks:
PowerShell:
Invoke-RestMethod -Uri http://127.0.0.1:5000/tasks -Method Get
curl:
curl http://127.0.0.1:5000/tasks
Example Response:
[
  {"id": 1, "title": "Learn Flask", "done": false},
  {"id": 2, "title": "Build a REST API", "done": false}
]

To POST (add) a new task:
PowerShell:
Invoke-RestMethod -Uri http://127.0.0.1:5000/tasks -Method Post -Body '{"title": "Finish Day 4 Task"}' -ContentType "application/json"
curl:
curl -X POST -H "Content-Type: application/json" -d '{"title": "Finish Day 4 Task"}' http://127.0.0.1:5000/tasks
Example Response:
{"id": 3, "title": "Finish Day 4 Task", "done": false}

To PUT (update) a task:
PowerShell:
Invoke-RestMethod -Uri http://127.0.0.1:5000/tasks/1 -Method Put -Body '{"title": "Learn Flask in detail", "done": true}' -ContentType "application/json"
curl:
curl -X PUT -H "Content-Type: application/json" -d '{"title": "Learn Flask in detail", "done": true}' http://127.0.0.1:5000/tasks/1
Example Response:
{"id": 1, "title": "Learn Flask in detail", "done": true}

To DELETE a task:
PowerShell:
Invoke-RestMethod -Uri http://127.0.0.1:5000/tasks/2 -Method Delete
curl:
curl -X DELETE http://127.0.0.1:5000/tasks/2
Example Response:
{"message": "Task deleted"}

Project Structure:
flask-api_4/
├── app.py        # Main application file
├── README.md     # Project documentation

