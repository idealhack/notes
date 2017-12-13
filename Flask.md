# Flask

## Overview

- [Welcome | Flask (A Python Microframework)](http://flask.pocoo.org/)

## Books

- http://exploreflask.com/

## Libraries

- https://github.com/coleifer/flask-peewee
- https://github.com/kennethreitz/flask-sockets
- https://github.com/flask-restful/flask-restful

## Issues

### Broken Pipe

#### Use `threaded`

    app.run(threaded=True)

#### Use `gevent.wsgi`

    from gevent.wsgi import WSGIServer
    http_server = WSGIServer(('', 5000), app)
    http_server.serve_forever()

#### Use other WSGI Server

- http://gunicorn.org/
- http://projects.unbit.it/uwsgi/
- http://flask.pocoo.org/docs/0.12/deploying/uwsgi/#configuring-nginx
