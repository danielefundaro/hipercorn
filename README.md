# hipercorn

[![Docker build](https://img.shields.io/docker/automated/fundanie/hipercorn)](https://hub.docker.com/r/fundanie/hipercorn)


Docker image with hypercorn ASGI and python 3.9.11 that you can use as a base image for your project. Define your Dockerfile as shown below:

    FROM hypercorn:latest
    
    # install dependecies
    COPY ./requirements.txt ./requirements.txt
    RUN pip install -r requirements.txt

    # copies the entire project folder, containing the main application
    COPY ./app ./app

    # expose port
    EXPOSE 8000

    ENTRYPOINT ["hypercorn", "-b", "0.0.0.0:8000", "./app/main:app"]
