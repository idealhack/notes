# Flask

## Overview

- [Welcome | Flask (A Python Microframework)](http://flask.pocoo.org/)

## Books

- [Explore Flask — Explore Flask 1.0 documentation](http://exploreflask.com/)

## Libraries

- [coleifer/flask-peewee: flask integration for peewee, including admin, authentication, rest api and more](https://github.com/coleifer/flask-peewee)
- [kennethreitz/flask-sockets: Elegant WebSockets for your Flask apps.](https://github.com/kennethreitz/flask-sockets)
- [flask-restful/flask-restful: Simple framework for creating REST APIs](https://github.com/flask-restful/flask-restful)

## Issues

### Broken Pipe

#### Use `threaded`

    app.run(threaded=True)

#### Use `gevent.wsgi`

    from gevent.wsgi import WSGIServer
    http_server = WSGIServer(('', 5000), app)
    http_server.serve_forever()

#### Use other WSGI Server

- [Gunicorn - Python WSGI HTTP Server for UNIX](http://gunicorn.org/)
- [The uWSGI project — uWSGI 2.0 documentation](http://projects.unbit.it/uwsgi/)
- [uWSGI — Flask Documentation (0.12)](http://flask.pocoo.org/docs/0.12/deploying/uwsgi/#configuring-nginx)
