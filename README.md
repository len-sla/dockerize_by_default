## Project Name
> <p>Dockerising by default.<br>
To change constantly try new environments flexible base is one of the necessary things.<br>
At best  working on as many as possible operating systems. here are comming couple of contenerisations players.<br>
When we are talking about small scale up to 200 instances: docker and docker swarm is one of the choices. <br>
 
Docker allows for containerization of applications, which means you can run isolated instances of your services and applications. <br> In addition, Docker gives you the ability to connect your apps and services together with Docker Compose, which makes Python apps very convenient to build.<br>
 
Below there are cases where in my learning and work with docker was really game changer.
For that reason I will not be expaining what is image container, docker-compose etc. 
It will be more about examples like " for doing ML or NLP or other task I took particualr image ajusted and made it work.

Someone could ask what about Virtual Machines?<br>
Contrary to how VMs work, with Docker we don’t need to constantly set up clean environments in the hopes of avoiding conflicts.<br>
With Docker, we know that there will be no conflicts. Docker guarantees that application microservices will run in their own environments that are completely separate from the operating system.

Thanks to Docker, there’s no need for each developer in a team to carefully follow 20 pages of operating system-specific instructions. <br>Instead, one developer can create a stable environment with all the necessary libraries and languages and simply save this setup in the Docker Hub or other server.




### General info
If you want to start a journey on high seas it is good to learn from the best .
like people who  own title of capitain docker.
One of that group is Lulasz Lach(https://lach.dev/ | https://github.com/lukaszlach/). <br>I learned couple of trics which mage my life easier with ML, NLP and Python



 ---
netshoot
https://github.com/nicolaka/netshoot
 
 


First application which I am opening in my ubuntu is 
ctop from netshoot( created by Nicola Kabar ) to deal with all kind of network issues.<br>
docker run -it --rm -v /var/run/docker.sock:/var/run/docker.sock --name netshooot-ctop nicolaka/netshoot  ctop
 
![what for is netshoot](netshoot.png)

This will be my prevailing approach __not installing applications in the system__ if possible use applications the from container 


---




## 1.  certainly you need firefox or other browser( linux thats why -v /tmp/.X11-unix:/tmp/.X11-unix  )


--- 
```
docker run -d \
--name firefox \
-e DISPLAY=$DISPLAY \
-v /tmp/.X11-unix:/tmp/.X11-unix \
kennethkl/firefox
```
If there is need to do that in windows work of Jocelyn Le Sage is doing the job  https://github.com/jlesage/docker-firefox.
Well documented, bullet proff, up to date. There are also other tools and  I am not the only one who appreciate this repository.

 ```
 docker run -d \
    --name=firefox \
    -p 5800:5800 \
    -v /docker/appdata/firefox:/config:rw \
    --shm-size 2g \
    jlesage/firefox
 ```
 
 
---

## 2.  why no to use VSCode itself in docker
```bash
docker run -it \
    -p 8080:8080 \
    -v "$PWD:/home/coder/project" \
    -u "$(id -u):$(id -g)" \
    codercom/code-server
```
## 3.  and stanza from Stanford
 https://github.com/NLPbox/stanford-corenlp-docker
 
 ```
 docker run --rm --name stanza_nlp -p 9000:9000 nlpbox/corenlp
 ```
 end voilà:
 
 ![Docker](https://github.com/len-sla/dockerize_by_default/blob/main/docker-1.PNG)
 
 ## 4.  [Data science container](https://github.com/andreivmaksimov/python_data_science)

It is nicely described how to prepare own conrtainer with jupyter keras pandas and tensorflow 
to be able check own ideas

This is fully ready Docker container with:

    NumPy
    Pandas
    Sklearn
    Matplotlib
    Seaborn
    pyyaml
    h5py
    Jupyter
    Tensorflow
    Keras
    OpenCV 3


https://github.com/andreivmaksimov/python_data_science
### Status
Project is: _in progress_ 





## To monitor what is going on with docker containers
 
 we could start from the simplest
 .  and stanza from Stanford
 https://github.com/NLPbox/stanford-corenlp-docker
 
 ```
docker stats
 ```
 a bit more advances with the use of other docker container ctop
 
 ```
docker stats
 ```


### Contact
Created by: _lencz.sla@gmail.com_

