<!-- omit in toc -->
# Introduction
How to build a Python API?

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [1. WSGI (Web Server Gateway Interface)](#1-wsgi-web-server-gateway-interface)
  - [2. ASGI (Asynchronous Server Gateway Interface)](#2-asgi-asynchronous-server-gateway-interface)
- [Package](#package)
  - [1. PyJWT](#1-pyjwt)
  - [2. uvicorn](#2-uvicorn)
  - [3. Swagger](#3-swagger)
- [Commands](#commands)
  - [1. Install FastAPI](#1-install-fastapi)
  - [2. FlaskAPI](#2-flaskapi)
    - [2.1. create an instance of this class](#21-create-an-instance-of-this-class)
    - [2.2. to register a view function for a given URL rule](#22-to-register-a-view-function-for-a-given-url-rule)
    - [2.3. run the flask application](#23-run-the-flask-application)
- [Flask Issue: cannot import name 'escape' from 'jinja2'](#flask-issue-cannot-import-name-escape-from-jinja2)


<br />

# Fundamental Concepts

## 1. WSGI (Web Server Gateway Interface)
* **WSGI server** means servers following WSFI rules. e.g. gunicorn, uwsgi 
* to provide the interface between Python web application and web server
* provided a standard for **synchronous** Python apps

<br />

## 2. ASGI (Asynchronous Server Gateway Interface)
* a spiritual successor to WSGI
* provides one for both **asynchronous** and synchronous apps

<br />

# Package

## 1. PyJWT
* to encode and decode JSON Web Tokens (JWT)

<br />

## 2. uvicorn
* an ASGI web server implementation for Python

<br />

## 3. Swagger
* Auto-generate documentation from an API definition
* http://host:port/docs

<br />

# Commands

## 1. Install FastAPI

  ```sh
  pipenv install fastapi==version
  ```

<br />

## 2. FlaskAPI

### 2.1. create an instance of this class
  ```python
  app = Flask(__name__)
  ```

<br />

### 2.2. to register a view function for a given URL rule

  ```python
  # 'Hello world' will be printed when triggering "host+port:/" on the website

  @app.route('/', methods=['GET'])
  def index():
      return 'Hello World'
  ```
    

* default_config = {'APPLICATION_ROOT': '/', ...}


### 2.3. run the flask application
Runs the application on a **local development server**.
* Do not use run() in a **production** setting. It is not intended to meet **security** and **performance requirements** for a production server
* 
  ```python
  # Running on http://0.0.0.0:8888/
  app.run(host='0.0.0.0', port=8888)
  ```

  *  0.0.0.0 <br /> all IPv4 addresses on the local machine. This ensures that the server will be reachable from all addresses


# Flask Issue: cannot import name 'escape' from 'jinja2'
> Flask 1.X.X uses jinja with escape module. However, new version of jinja2 does not support escape. Therefore, update the version of Flask where jinja does not use escape module 

```s
  Flask==2.1.0
```
