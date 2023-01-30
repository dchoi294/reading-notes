# Class 31 Reading Notes

*Docker* is really just Linux containers which are a type of virtualization. Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm. How could multiple programmers use the same single machine? The answer was virtualization and specifically virtual machines which are complete copies of a computer system from the operating system on up.  

**Version**  
```
$ docker --version
Docker version 19.03.5, build 633a0ea      #(ex)
# Latest version is 19

$ docker-compose --version
docker-compose version 1.24.1, build 4667896b    #(ex)
# At least 1.24.x
```

To confirm Docker installed correctly we can run our first command `docker run hello-world`. This will download an official image and then run the container. We’ll discuss both images and containers shortly.  
A good command to inspect Docker is `docker info` which we can run now. It will contain a lot of output but focus on the top lines which show we now have 1 container which is `stopped` and 1 image.

First create a local directory on your computer for our code. I’ve chosen to make a code folder on my Desktop (I’m using an Apple computer) and then a python3.7 folder within that.  
```
$ cd ~/Desktop
$ mkdir code && cd code
$ mkdir python3.7 && cd python3.7
```
Now we need to define the image with a Dockerfile. This is similar to a Pipenv or a requirements.txt file; it is a list of all the requirements needed to build our image. It is simpler to have them all in one place rather than install each manually line-by-line.

*Django for APIs*  
Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework. It always must be added to a project after Django itself has been installed and configured.  

Navigate to the existing code directory on the Desktop and make sure you are not in a current virtual environment. You should not see (.venv) before the shell prompt. If you do, use the command deactivate to leave it. Make a new directory called library, create a new virtual environment, activate it, and install Django.  
```
> cd onedrive\desktop\code
> mkdir library
> cd library
> python -m venv .venv
> .venv\Scripts\Activate.ps1
(.venv) > python -m pip install django~=4.0.0
```


Reference [Beginner’s Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)  
Reference [Django for APIs - Library Website](https://djangoforapis.com/library-website-and-api/)

## Things I want to know more about

[Back to Home](../../README.md)
