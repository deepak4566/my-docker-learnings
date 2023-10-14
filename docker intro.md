## What is a container ?

A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another.
A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools,
system libraries and settings.

Ok, let me make it easy !!!

A container is a bundle of Application, Application libraries required to run your application and the minimum system dependencies.

## why countainers are light weight 
countainers doesnt have own os ,but just have some system dependencies and functions , countainers uses host os so its very light weight 
campared to virtual machine ,vm has own os (heavy size)

## install docker 
```shell

sudo apt update
sudo apt install docker.io -y
```
## start docker with defult command 
```
docker run hello-world
```
If the output says:

```
docker: Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/create": dial unix /var/run/docker.sock: connect: permission denied.
See 'docker run --help'.
```

This can mean two things, 
1. Docker deamon is not running.
2. Your user does not have access to run docker commands.


### Start Docker daemon

You use the below command to verify if the docker daemon is actually started and Active

```
sudo systemctl status docker
```

If you notice that the docker daemon is not running, you can start the daemon using the below command

```
sudo systemctl start docker
```


### Grant Access to your user to run docker commands

To grant access to your user to run the docker command, you should add the user to the Docker Linux group. Docker group is create by default when docker is installed.

```
sudo usermod -aG docker ubuntu
```

In the above command `ubuntu` is the name of the user, you can change the username appropriately.

**NOTE:** : You need to logout and login back for the changes to be reflected.


### Docker is Installed, up and running 🥳🥳

Use the same command again, to verify that docker is up and running.

```
docker run hello-world
```

Output should look like:

```
....
....
Hello from Docker!
This message shows that your installation appears to be working correctly.
...
...
```

### Build your first Docker Image

You need to change the username accoringly in the below command

```
docker build -t image-tag .
```
here . (dot) reperent to build trher dockerfile present in same dictionary
-t is tag very much important 

### Run your First Docker Container

```
docker run -it image-tag 

```
here it means interactive terminal

### Push the Image to DockerHub and share it with the world

```
docker push image-tag
```

