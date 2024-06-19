# Python on Whales

Docs: [Python on Whales](https://gabrieldemarmiesse.github.io/python-on-whales/)

- 1 to 1 mapping between the CLI interface and the Python API. No need to look in the docs what is the name of the function/argument you need.
- Docker object as Python objects: Container, Images, Volumes, Services... and their attributes are updated in real-time!
- Each Docker object can be used as a context manager. When getting out of the context, the Docker object is removed automatically, even if an exception occurs.
- In a sense this project is built on top of Docker-py because the implementation, the organisation and the API is inspired from the project, but the codebases could not be the same.
- 
```
docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```
becomes
```
from python_on_whales import docker

docker.run(
    "postgres:9.6",
    name="some-postgres",
    envs={"POSTGRES_PASSWORD": "mysecretpassword"},
    detach=True,
)
print(docker.ps())
# [python_on_whales.Container(id='f5fb939c409d', name='some-postgres')]
```

We have seen in other Docker examples the use of ARG:
```
ARG BaseImage
FROM $BaseImage
```
and this means we can use this and other shell variables to script a lot of processes and create our own testing matrix.

Some uses to follow...

<br>

