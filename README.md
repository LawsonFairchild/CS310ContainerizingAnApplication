1. I made the dockerfile by following a tutorial I found on the internet. First I set the version of python I was using using "FROM python:3.13".
  Next I set the working directory using "WORKDIR /home/Lawson/SimpleFlask".
  Next I copied the contents of the src folder to the filesystem of the container using "COPY src ./src".
  Next I specified which port to expose using "EXPOSE 8080".
  Next I specified added a user and specified the program as that user since this app does not need root access to run (principle of least privelage) using "RUN useradd app" and "USER app".
  Finally I specified the command for docker to run:
    uvicorn ~ app running the container
    app.simple_flask:app ~ tells uvicorn that there is a application called app in simple_flask.py and to name the app app.
    --host 0.0.0.0 ~ lets the website be seen by other computers
    --port 8080 ~ sets the port to 8080
2. I used:
  "sudo docker build ." to create an image
  "sudo docker images" to find the name of the image
  "sudo docker run hello-world" to run the image
