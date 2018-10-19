# Python 3.7 + Gunicorn + Flask + Flask-RESTplus

FROM python:3.7

WORKDIR /usr/src/app

COPY requirements.txt ./

RUN python3 -m pip install --upgrade pip setuptools && \
    python3 -m pip install --no-cache-dir -r requirements.txt

COPY main.py ./

CMD [ "python3", "./main.py" ]