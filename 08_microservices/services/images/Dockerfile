# pull official base image
FROM python:3.13-slim 

# install system dependencies
RUN apt-get update && apt-get install -y netcat-openbsd dos2unix

# set work directory
WORKDIR /usr/src/app

# copy project
COPY . /usr/src/app/

# install dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt
RUN dos2unix /usr/src/app/entrypoint.sh
RUN chmod u+x /usr/src/app/entrypoint.sh

EXPOSE 5000

ENTRYPOINT ["/bin/sh", "/usr/src/app/entrypoint.sh"]