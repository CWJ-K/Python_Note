# FlaskAPI

    app = Flask(__name__)
    @app.route('/', methods=['GET'])
    # route: / => root

    app.run(host='0.0.0.0', port=8888)
    # 0.0.0.0: not use local host, use 
    #https://stackoverflow.com/questions/31904761/what-does-app-runhost-0-0-0-0-mean-in-flask


## Package: PyJWT
https://joehuang-pop.github.io/2020/03/01/Python-PyJWT-%E5%8A%A0%E8%A7%A3%E5%AF%86%E6%A8%A1%E7%B5%84-encode-decode/


# FastAPI
    pipenv install fastapi==version
## Package: uvicorn
## Swagger
http://127.0.0.1:8888/docs