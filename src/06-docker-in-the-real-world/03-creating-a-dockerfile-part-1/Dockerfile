FROM python:3.7.7-alpine3.11

RUN mkdir /app
WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY  . .

LABEL maintainer="pccodes <pascal.email.com>" \
    version="1.0"

CMD flask run --host=0.0.0.0 --port=5000