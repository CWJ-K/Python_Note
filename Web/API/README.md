<!-- omit in toc -->
# Introduction
Take note of Python API

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [WSGI (Web Server Gateway Interface)](#wsgi-web-server-gateway-interface)
  - [ASGI (Asynchronous Server Gateway Interface)](#asgi-asynchronous-server-gateway-interface)
- [Package](#package)
  - [PyJWT](#pyjwt)
  - [uvicorn](#uvicorn)
  - [Swagger](#swagger)
- [Commands](#commands)
  - [Install FastAPI](#install-fastapi)
  - [FlaskAPI](#flaskapi)
    - [create an instance of this class](#create-an-instance-of-this-class)
    - [to register a view function for a given URL rule](#to-register-a-view-function-for-a-given-url-rule)
    - [run the flask application](#run-the-flask-application)


<br />

# Fundamental Concepts

## WSGI (Web Server Gateway Interface)
* **WSGI server** means servers following WSFI rules. e.g. gunicorn, uwsgi 
* to provide the interface between Python web application and web server
* provided a standard for **synchronous** Python apps


## ASGI (Asynchronous Server Gateway Interface)
* a spiritual successor to WSGI
* provides one for both **asynchronous** and synchronous apps

<br />

# Package

## PyJWT
* to encode and decode JSON Web Tokens (JWT)

<br />

## uvicorn
* an ASGI web server implementation for Python

<br />

## Swagger
* Auto-generate documentation from an API definition
* http://host:port/docs

<br />

# Commands
## Install FastAPI

    pipenv install fastapi==version


## FlaskAPI

### create an instance of this class
    app = Flask(__name__)


### to register a view function for a given URL rule

    # 'Hello world' will be printed when triggering "host+port:/" on the website

    @app.route('/', methods=['GET'])
    def index():
        return 'Hello World'
    

* default_config = {'APPLICATION_ROOT': '/', ...}


### run the flask application
Runs the application on a **local development server**.
* Do not use run() in a **production** setting. It is not intended to meet **security** and **performance requirements** for a production server
* 
        # Running on http://0.0.0.0:8888/
        app.run(host='0.0.0.0', port=8888)

  *  0.0.0.0 <br /> all IPv4 addresses on the local machine. This ensures that the server will be reachable from all addresses