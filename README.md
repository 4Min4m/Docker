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

Part 2 : 

1️⃣ ADD: Similar to COPY, but with added features. It can handle URLs and automatically unpack archives. Example:

ADD https://example[dot]com/app.tar.gz /app/

This fetches 'app.tar.gz' from the web and unpacks it into '/app/'.

2️⃣ VOLUME: Creates a mount point for external volumes. Used to share data between the host and container. Example:

VOLUME /data

This creates a volume named '/data' where data can be persisted outside the container.

3️⃣ USER: Specifies the user to use when running the container. Helps improve security by avoiding running as root. Example:

USER appuser

This sets the user to 'appuser' in the container.

4️⃣ LABEL: Adds metadata to the image in key-value format. Useful for versioning and documenting the image. Example:

LABEL version="1.0" maintainer="John Doe"

This adds version and maintainer labels to the image.

5️⃣ ARG: Similar to ENV, but used during build time only. It doesn't persist in the final image. Example:

ARG BUILD_ENV=production

This sets the 'BUILD_ENV' argument with a default value of 'production'.

6️⃣ ONBUILD: Triggers instructions to be executed when this image is used as a base for another image. Example:

ONBUILD COPY . /app

This copies the current directory's content into '/app' when this image is used as a base.

7️⃣ STOPSIGNAL: Sets the system call signal that will be sent to the container to stop it gracefully. Example:

STOPSIGNAL SIGINT

This sets the SIGINT signal as the stop signal.

8️⃣ HEALTHCHECK: Defines a command to check the container's health. Helps monitor the app's status. Example:

HEALTHCHECK CMD curl -f http://localhost/ || exit 1

This checks if 'http://localhost/' is reachable, failing if it's not.

9️⃣ SHELL: Overrides the default shell used by RUN, CMD, and ENTRYPOINT. Example:

SHELL ["/bin/bash", "-c"]

This sets '/bin/bash -c' as the shell for subsequent commands.

🔟 .dockerignore: Not a parameter, but a crucial file. Works like .gitignore to exclude files from the image. Example:

*.log
node_modules/

This ignores log files and the 'node_modules' directory during the build.
