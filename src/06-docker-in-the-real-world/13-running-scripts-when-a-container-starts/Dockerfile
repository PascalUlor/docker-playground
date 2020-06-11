# Updates:
#   Nov 2019: Update base Docker image to use a more recent version of Python
#             You can also use python:3.7.5-slim-buster for a Debian image
FROM python:3.7.5-alpine

RUN mkdir /app
WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .

LABEL maintainer="Nick Janetakis <nick.janetakis@gmail.com>" \
      version="1.0"

VOLUME ["/app/public"]

COPY docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh
ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]
