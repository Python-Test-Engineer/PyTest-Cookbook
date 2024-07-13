# Multiple container testing

This is inspired by the excellent courst 'Python in Containers' on Udemy.

We build a flask image and this is used as one layer for another image for testing.

An explainer video is here: [YouTube Video](https://youtu.be/Jsf5S8cZj1Y).

The repo is [here](https://github.com/Python-Test-Engineer/yt-docker-flask-pytest-pdb).

It introduces the use of Docker's ARG, where we can specify at build time another image. 

Generally, nothing can come before FROM as this creates a new shell as it were.

However, we can use ARG to be able to pass in arguments in the CLI build:

### Base Image
```
ARG BaseImage
FROM $BaseImage
```

### use --build-arg 
```
docker build -t factors_flask_tester -f Dockerfile.tester --build-arg BaseImage=factors_flask_pdb .
```

Tests are carried out on the `factors_flask_tester` image.

Note, we can use the -f flag to select a Dockerfile. This can be a convenience when we have several Dockerfiles we want to use but don't want to have to overwrite the root Dockerfile.

<br>