## 0x05. AirBnB clone - RESTful API

![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Back-end](https://img.shields.io/badge/Back--end-black?style=for-the-badge)
![API](https://img.shields.io/badge/API-red?style=for-the-badge)
![Webserver](https://img.shields.io/badge/Webserver-blue?style=for-the-badge)
![Flask](https://img.shields.io/badge/Flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)

### Concepts

* **For this project, we expect you to look at these concepts:**

### [1] REST API

REST API is a software architectural style for Backend.

**REST = “REpresentational State Transfer”. API = Application Programming Interface**

Its purpose is to induce performance, scalability, simplicity, modifiability, visibility, portability, and reliability.

REST API is **Resource-based**, a resource is an object and can be access by a URI. An object is “displayed”/transferred via a **representation** (typically JSON). HTTP methods will be actions on a resource.

* Example:

  - Resource: `Person` (John)
  - Service: contact information (`GET`)
  - Representation:
	- `first_name`, `last_name`, `date_of_birth`
	- JSON format

## There are 6 constraints:

### 1. Uniform Interface

- Define the interface between client-server
- Simple and can be split in small parts

* **HTTP verbs**

  - `GET`:
	- Read representation of a resource or a list of resources

  - `POST`:

	- Create a new resource
  - `PUT`:

	- Update an existing resource

  - `DELETE`:

	- Remove an existing resource

### URIs - resource name

* A resource representation is accessible by a URI:

	- `GET /users`: path for listing all user resources
	- `GET /users/12`: path for the user `id = 12`
	- `GET /users/12/addresses`: path for listing all addresses of the user `id = 12`
	- `POST /users`: path for creating a user resource
	- `PUT /users/12`: path for updating the user `id = 12`
	- `DELETE /users/12/addresses/2`: path for deleting the address `id = 2` of the user `id = 12`

### HTTP Response

* In the HTTP Response, the client should verify the information of two things:

	- status code: result of the action
	- body: JSON or XML representation of resources

* Some important status code:

	- `200`: OK
	- `201`: created => after a `POST` request
	- `204`: no content => can be return after a `DELETE` request
	- `400`: bad request => the server doesn’t understand the request
	- `401`: unauthorized => client user can’t be identified
	- `403`: forbidden => client user is identified but not allowed to access a resource
	- `404`: not found => resource doesn’t exist
	- `500`: internal server error

### 2. Stateless

The server is independent of the client. The server doesn’t store user client information/state. Each request contains enough context to process it (HTTP Headers, etc.)

Some authentication systems like OAuth have to store information on the server side but they do it with REST API design.

### 3. Cacheable

* All server responses (resource representation) are cacheable:

	- Explicit
	- Implicit
	- Negotiated

Caches are here to improve performances. In a REST API, clients don’t care about the caching strategy, if the resource representation comes from a cache or from a database…

### 4. Client-Server

REST API is designed to separate Client from the Server. The server doesn’t know who is talking to it. Clients are not concerned with data storage => the portability of client code is improved. Servers are not concerned with the user interface or user state so that servers can be simpler and more scalable

### 5. Layered System

Client can’t assume direct connection to server. Intermediary servers may improve system scalability by enabling load-balancing and by providing shared caches. Layers may also enforce security policies.

### 6. Code on Demand (optional)

* Server can temporarily:

	- Transfer logic to client
	- Allow client to execute logic
	- Example: JavaScript

[2] [AirBnB clone](https://github.com/Abner261/AirBnB_clone_v2/blob/master/README.md)

### Resources

* **Read or watch:**

	- **REST API** concept page
	- [Learn REST: A RESTful Tutorial](https://www.restapitutorial.com/)
	- [Designing a RESTful API with Python and Flask](https://blog.miguelgrinberg.com/post/designing-a-restful-api-with-python-and-flask)
	- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
	- [Flask cheatsheet](https://s3.amazonaws.com/intranet-projects-files/holbertonschool-higher-level_programming+/301/flask_cheatsheet.pdf)
	- [What are Flask Blueprints, exactly?](https://stackoverflow.com/questions/24420857/what-are-flask-blueprints-exactly)
	- [Flask](https://palletsprojects.com/p/flask/)
	- [Modular Applications with Blueprints](https://flask.palletsprojects.com/en/1.1.x/blueprints/)
	- [Flask tests](https://flask.palletsprojects.com/en/1.1.x/testing/)
	- [Flask-CORS](https://flask-cors.readthedocs.io/en/latest/)

* **Learning Objectives**

	- At the end of this project, you are expected to be able to [explain to anyone](), **without the help of Google:**

* **General**

	- What REST means
	- What API means
	- What CORS means
	- What is an API
	- What is a REST API
	- What are other type of APIs
	- Which is the HTTP method to retrieve resource(s)
	- Which is the HTTP method to create a resource
	- Which is the HTTP method to update resource
	- Which is the HTTP method to delete resource
	- How to request REST API

### Requirements

* **Python Scripts**

	- Allowed editors: `vi`, `vim`, `emacs`
	- All your files will be interpreted/compiled on Ubuntu 20.04 LTS using `python3` (version 3.4.3)
	- All your files should end with a new line
	- The first line of all your files should be exactly `#!/usr/bin/python3`
	- A `README.md` file, at the root of the folder of the project, is mandatory
	- Your code should use the `PEP 8` style (version 1.7)
	- All your files must be executable
	- The length of your files will be tested using `wc`
	- All your modules should have documentation (`python3 -c 'print(__import__("my_module").__doc__)'`)
	- All your classes should have documentation (`python3 -c 'print(__import__("my_module").MyClass.__doc__)'`)
	- All your functions (inside and outside a class) should have documentation (`python3 -c 'print(__import__("my_module").my_function.__doc__)'` and `python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'`)
	- A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class or method (the length of it will be verified)

* **Python Unit Tests**

	- Allowed editors: `vi`, `vim`, `emacs`
	- All your files should end with a new line
	- All your test files should be inside a folder `tests`
	- You have to use the [unittest module](https://docs.python.org/3.4/library/unittest.html#module-unittest)
	- All your test files should be python files (extension: `.py`)
	- All your test files and folders should start by `test_`
	- Your file organization in the tests folder should be the same as your project: ex: for `models/base_model.py`, unit tests must be in: `tests/test_models/test_base_model.py`
	- All your tests should be executed by using this command: `python3 -m unittest discover tests`
	- You can also test file by file by using this command: `python3 -m unittest tests/test_models/test_base_model.py`
	- We strongly encourage you to work together on test cases, so that you don’t miss any edge cases

## More Info

![Server side](https://github.com/Abner261/README_File_For_AirBnB_clone_V3/blob/master/Server%20side%20vs%20Client%20side.png?raw=true)

### Install Flask

```sh
$ pip3 install Flask
```

### Video library

## Tasks

0. [Restart from scratch!](AirBnB_clone_v3)

No no no! We are already too far in the project to restart everything.

But once again, let’s work on a new codebase.

* For this project you will fork this [codebase](https://github.com/alexaorrico/AirBnB_clone_v2):

  - Update the repository name to `AirBnB_clone_v3`
  - Update the `README.md`:
	- Add yourself as an author of the project
	- Add new information about your new contribution
	- Make it better!
* If you’re the owner of this codebase, create a new repository called `AirBnB_clone_v3` and copy over all files from `AirBnB_clone_v2`

* **Repo:**

	- GitHub repository: `AirBnB_clone_v3`

1. [Never fail!](AirBnB_clone_v3)

![Here we Go](https://github.com/Abner261/README_File_For_AirBnB_clone_V3/blob/master/Never%20fail.jpg?raw=true)

Since the beginning we’ve been using the `unittest` module, but do you know why `unittests` are so important? Because when you add a new feature, you refactor a piece of code, etc… you want to be sure you didn’t break anything.

* At Holberton, we have a lot of tests, and they all pass! Just for the Intranet itself, there are:

	- `5,213` assertions (as of 08/20/2018)
	- `13,061` assertions (as of 01/25/2021)

* The following requirements **must** be met for your project:

	- all current tests must pass (don’t delete them…)
	- add new tests as much as you can (tests are mandatory for some tasks)

```sh
guillaume@ubuntu:~/AirBnB_v3$ python3 -m unittest discover tests 2>&1 | tail -1
OK
guillaume@ubuntu:~/AirBnB_v3$ HBNB_ENV=test HBNB_MYSQL_USER=hbnb_test HBNB_MYSQL_PWD=hbnb_test_pwd HBNB_MYSQL_HOST=localhost HBNB_MYSQL_DB=hbnb_test_db HBNB_TYPE_STORAGE=db python3 -m unittest discover tests 2>&1 /dev/null | tail -n 1
OK
guillaume@ubuntu:~/AirBnB_v3$ 
```

**Repo:**

- GitHub repository: `AirBnB_clone_v3`

2. [Improve storage]()

Update DBStorage and FileStorage, adding two new methods. All changes should be done in the branch storage_get_count:

A method to retrieve one object:

Prototype: def get(self, cls, id):
cls: class
id: string representing the object ID
Returns the object based on the class and its ID, or None if not found
A method to count the number of objects in storage:

Prototype: def count(self, cls=None):
cls: class (optional)
Returns the number of objects in storage matching the given class. If no class is passed, returns the count of all objects in storage.
Don’t forget to add new tests for these 2 methods on each storage engine.

```sh
guillaume@ubuntu:~/AirBnB_v3$ cat test_get_count.py
#!/usr/bin/python3
""" Test .get() and .count() methods
"""
from models import storage
from models.state import State

print("All objects: {}".format(storage.count()))
print("State objects: {}".format(storage.count(State)))

first_state_id = list(storage.all(State).values())[0].id
print("First state: {}".format(storage.get(State, first_state_id)))

guillaume@ubuntu:~/AirBnB_v3$
guillaume@ubuntu:~/AirBnB_v3$ HBNB_MYSQL_USER=hbnb_dev HBNB_MYSQL_PWD=hbnb_dev_pwd HBNB_MYSQL_HOST=localhost HBNB_MYSQL_DB=hbnb_dev_db HBNB_TYPE_STORAGE=db ./test_get_count.py 
All objects: 1013
State objects: 27
First state: [State] (f8d21261-3e79-4f5c-829a-99d7452cd73c) {'name': 'Colorado', 'updated_at': datetime.datetime(2017, 3, 25, 2, 17, 6), 'created_at': datetime.datetime(2017, 3, 25, 2, 17, 6), '_sa_instance_state': <sqlalchemy.orm.state.InstanceState object at 0x7fc0103a8e80>, 'id': 'f8d21261-3e79-4f5c-829a-99d7452cd73c'}
guillaume@ubuntu:~/AirBnB_v3$
guillaume@ubuntu:~/AirBnB_v3$ ./test_get_count.py 
All objects: 19
State objects: 5
First state: [State] (af14c85b-172f-4474-8a30-d4ec21f9795e) {'updated_at': datetime.datetime(2017, 4, 13, 17, 10, 22, 378824), 'name': 'Arizona', 'id': 'af14c85b-172f-4474-8a30-d4ec21f9795e', 'created_at': datetime.datetime(2017, 4, 13, 17, 10, 22, 378763)}
guillaume@ubuntu:~/AirBnB_v3$
```

For this task, you must make a pull request on GitHub.com, and ask at least one of your peer to review and merge it.

**Repo:**

- GitHub repository: `AirBnB_clone_v3`
- File: `models/engine/db_storage.py, models/engine/file_storage.py, tests/test_models/test_engine/test_db_storage.py, tests/test_models/test_engine/test_file_storage.py`

3. [Status of your API]()

It’s time to start your API!

Your first endpoint (route) will be to return the status of your API:

```sh
guillaume@ubuntu:~/AirBnB_v3$ HBNB_MYSQL_USER=hbnb_dev HBNB_MYSQL_PWD=hbnb_dev_pwd HBNB_MYSQL_HOST=localhost HBNB_MYSQL_DB=hbnb_dev_db HBNB_TYPE_STORAGE=db HBNB_API_HOST=0.0.0.0 HBNB_API_PORT=5000 python3 -m api.v1.app
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
...
```

In another terminal:

```sh
guillaume@ubuntu:~/AirBnB_v3$ curl -X GET http://0.0.0.0:5000/api/v1/status
{
  "status": "OK"
}
guillaume@ubuntu:~/AirBnB_v3$ 
guillaume@ubuntu:~/AirBnB_v3$ curl -X GET -s http://0.0.0.0:5000/api/v1/status -vvv 2>&1 | grep Content-Type
< Content-Type: application/json
guillaume@ubuntu:~/AirBnB_v3$ 
```

Magic right? (No need to have a pretty rendered output, it’s a JSON, only the structure is important)

Ok, let starts:

Create a folder api at the root of the project with an empty file __init__.py
Create a folder v1 inside api:
create an empty file __init__.py
create a file app.py:
create a variable app, instance of Flask
import storage from models
import app_views from api.v1.views
register the blueprint app_views to your Flask instance app
declare a method to handle @app.teardown_appcontext that calls storage.close()
inside if __name__ == "__main__":, run your Flask server (variable app) with:
host = environment variable HBNB_API_HOST or 0.0.0.0 if not defined
port = environment variable HBNB_API_PORT or 5000 if not defined
threaded=True
Create a folder views inside v1:
create a file __init__.py:
import Blueprint from flask doc
create a variable app_views which is an instance of Blueprint (url prefix must be /api/v1)
wildcard import of everything in the package api.v1.views.index => PEP8 will complain about it, don’t worry, it’s normal and this file (v1/views/__init__.py) won’t be check.
create a file index.py
import app_views from api.v1.views
create a route /status on the object app_views that returns a JSON: "status": "OK" (see example)
Repo:

- GitHub repository: `AirBnB_clone_v3`
- File: `api/__init__.py, api/v1/__init__.py, api/v1/views/__init__.py, api/v1/views/index.py, api/v1/app.py`

4. Some stats?

Create an endpoint that retrieves the number of each objects by type:

In api/v1/views/index.py
Route: /api/v1/stats
You must use the newly added count() method from storage
guillaume@ubuntu:~/AirBnB_v3$ curl -X GET http://0.0.0.0:5000/api/v1/stats
{
  "amenities": 47, 
  "cities": 36, 
  "places": 154, 
  "reviews": 718, 
  "states": 27, 
  "users": 31
}
guillaume@ubuntu:~/AirBnB_v3$ 
(No need to have a pretty rendered output, it’s a JSON, only the structure is important)

Repo:

GitHub repository: AirBnB_clone_v3
File: api/v1/views/index.py

5. Not found
mandatory
Score: 0.0% (Checks completed: 0.0%)
Designers are really creative when they have to design a “404 page”, a “Not found”… 34 brilliantly designed 404 error pages

Today it’s different, because you won’t use HTML and CSS, but JSON!

In api/v1/app.py, create a handler for 404 errors that returns a JSON-formatted 404 status code response. The content should be: "error": "Not found"

```sh
guillaume@ubuntu:~/AirBnB_v3$ curl -X GET http://0.0.0.0:5000/api/v1/nop
{
  "error": "Not found"
}
guillaume@ubuntu:~/AirBnB_v3$ curl -X GET http://0.0.0.0:5000/api/v1/nop -vvv
*   Trying 0.0.0.0...
* TCP_NODELAY set
* Connected to 0.0.0.0 (127.0.0.1) port 5000 (#0)
> GET /api/v1/nop HTTP/1.1
> Host: 0.0.0.0:5000
> User-Agent: curl/7.51.0
> Accept: */*
> 
* HTTP 1.0, assume close after body
< HTTP/1.0 404 NOT FOUND
< Content-Type: application/json
< Content-Length: 27
< Server: Werkzeug/0.12.1 Python/3.4.3
< Date: Fri, 14 Apr 2017 23:43:24 GMT
< 
{
  "error": "Not found"
}
guillaume@ubuntu:~/AirBnB_v3$ 
```

**Repo:**

- GitHub repository: `AirBnB_clone_v3`
- File: `api/v1/app.py`

6. [State]()

Create a new view for State objects that handles all default RESTFul API actions:

In the file api/v1/views/states.py
You must use to_dict() to retrieve an object into a valid JSON
Update api/v1/views/__init__.py to import this new file
Retrieves the list of all State objects: GET /api/v1/states

Retrieves a State object: GET /api/v1/states/<state_id>

If the state_id is not linked to any State object, raise a 404 error
Deletes a State object:: DELETE /api/v1/states/<state_id>

If the state_id is not linked to any State object, raise a 404 error
Returns an empty dictionary with the status code 200
Creates a State: POST /api/v1/states

You must use request.get_json from Flask to transform the HTTP body request to a dictionary
If the HTTP body request is not valid JSON, raise a 400 error with the message Not a JSON
If the dictionary doesn’t contain the key name, raise a 400 error with the message Missing name
Returns the new State with the status code 201
Updates a State object: PUT /api/v1/states/<state_id>

If the state_id is not linked to any State object, raise a 404 error
You must use request.get_json from Flask to transform the HTTP body request to a dictionary
If the HTTP body request is not valid JSON, raise a 400 error with the message Not a JSON
Update the State object with all key-value pairs of the dictionary.
Ignore keys: id, created_at and updated_at
Returns the State object with the status code 200
