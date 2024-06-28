# Manage Docker with Python

Repo: [yt-docker-managed-by-python](https://github.com/Python-Test-Engineer/yt-docker-managed-by-python)

Video: to follow...

There are two main libraries for this:

1. Docs: [Python on Whales](https://gabrieldemarmiesse.github.io/python-on-whales/)
2. Docs: [Docker Py](https://docker-py.readthedocs.io/en/stable/)

For Python on Whales, a very useful script is:

```
from python_on_whales import DockerClient

docker = DockerClient(compose_files=["../docker-compose.yml"])

docker.compose.build()
docker.compose.up(detach=True)

# docker.compose.down()

```
By using a docker-compose.yaml file, we can use PyYaml to read, write and edit these files, enabling programatic customisation and creation of containers.

Another example is :
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
which can also be managed programatically.

For Docker-Py we have:

```
import docker
client = docker.from_env()
image = client.images.pull("redis")
output = client.containers.run("ubuntu", "echo hello world")
output = output.decode("utf-8")
print(str(output))

containers = client.containers.list()
for container in containers:
    print(container.name)
PORT = random.randint(8000, 9000)
container = client.containers.run("nginx:latest", detach=True, ports={"80/tcp": PORT})
```

Docker enables the use of ARG and --build-arg to add arguments prior to FROM, FROM usually being the first allowed command

```
ARG BaseImage
FROM $BaseImage
```
and this means we can use this and other shell variables to script a lot of processes and create our own testing matrix.

For the Docker Py library we have:

```
import docker
client = docker.from_env()
image = client.images.pull("redis")
output = client.containers.run("ubuntu", "echo hello world")
output = output.decode("utf-8")
print(str(output))

containers = client.containers.list()
for container in containers:
    print(container.name)
PORT = random.randint(8000, 9000)
container = client.containers.run("nginx:latest", detach=True, ports={"80/tcp": PORT})
```

Sources of YT video on Python and YAML

1. [MathByte](https://www.youtube.com/watch?v=sFqdgG8tSPk) - shorter and more concise video with its repo installed in this project in `yaml` folder.

2. [DevOpsMadeEasy](https://github.com/kunchalavikram1427/YouTube_Series/tree/main/YAML) which has a YT video (1hr 45m) [here](https://www.youtube.com/watch?v=GOk4IoYhM9U).

The repo and video explore managing Docker programatically with Python, mostly through the use of editing docker compose files and then running them programatically.

<br>

