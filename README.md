# Docker
Mastering Dockerfile
Mastering Docker File 🐳
Part 1
Remember sharing is caring 😉

Dockerfiles are key to building Docker images, so let's dive in! 

1️⃣ FROM: This sets the base image for your Docker image. It's like the starting point for your container. For example:

FROM ubuntu:20.04

This uses the official Ubuntu 20.04 image as the base.

2️⃣ RUN: Executes commands during the build process. Used to install packages or run any necessary setup tasks. For instance:

RUN apt-get update && apt-get install -y python3

This installs Python 3 in the image.

3️⃣ COPY: Copies files from the host to the container's filesystem. Great for adding application code. Example:

COPY app.py /app/

This copies the 'app.py' file from the host to '/app/' in the container.

4️⃣ WORKDIR: Sets the working directory within the container. Subsequent commands will run from this location. Example:

WORKDIR /app

This sets '/app' as the working directory.

5️⃣ EXPOSE: Specifies the port on which the container will listen. It does not publish the port to the host. Example:

EXPOSE 8080

This exposes port 8080 within the container.

6️⃣ CMD: Defines the default command to run when the container starts. It's often the main process of the app. Example:

CMD ["python3", "app.py"]

This runs 'python3 app.py' when the container starts.

7️⃣ ENV: Sets environment variables within the container. Useful for configuring the application. Example:

ENV DEBUG=True

This sets the 'DEBUG' environment variable to 'True'.

8️⃣ ARG: Defines build-time arguments. They can be passed using the --build-arg flag during image build. Example:

ARG VERSION=latest

This sets the 'VERSION' argument with a default value of 'latest'.

9️⃣ ENTRYPOINT: Similar to CMD, but provides an entry point for d container. The CMD will be arguments to this entry point. Example:

ENTRYPOINT ["python3"]
CMD ["app.py"]

This sets 'python3' as the entry point & 'app.py' as the default argument.

#Docker #Dockerfile #Containerization
