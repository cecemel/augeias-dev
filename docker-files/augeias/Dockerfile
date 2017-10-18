FROM python:2.7

RUN apt-get update
RUN apt-get install sed -y
RUN apt-get install libmagic1 -y

COPY requirements.txt /app/
COPY requirements-dev.txt /app/

RUN mkdir -p /root/data/cheeses
RUN mkdir -p /root/data/trees

WORKDIR "/app"
ARG GITUSER="USERNAME_NEEDED"
ARG GITPW="PASSWORD_NEEDED"

RUN pip install -r requirements.txt
RUN pip install -r requirements-dev.txt

COPY . /app

RUN python setup.py install

# Serve
CMD pserve development.ini
