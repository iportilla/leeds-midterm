<h1 align="center" style="border-bottom: none;">🔎 Docker 101 </h1>
<h3 align="center">Docker is an open-source project that automates the deployment of software applications inside containers by providing an additional layer of abstraction and automation of OS-level virtualization on Linux..</h3>


### Flow

In this course, you'll follow a series of hands-on exercises that demonstrate how to use containers for your applications. You'll start with the basics: creating and running your first Docker containers. By the end of the course, you'll get a brief introduction to running containers in production.


Enjoy the course!

<h3>BAIM-4200</h3>
</p>


# Energy Savings Chatbot Example


## Building and Publishing the Chatbot Example

1. Clone this git repository:

```bash
cd ~   # or wherever you want
git clone https://github.com/iportilla/leeds-midterm.git
cd ~/leeds-midterm
```

2. Update the index.html page with your chatbot details:

```bash
nano (or vi) public-html/index.html
```

For example:

```script
<script>
  window.watsonAssistantChatOptions = {
    integrationID: "08642bc1-7afe-404a-b41b-77ab7a2c01e0", // The ID of this integration.
    region: "us-south", // The region your integration is hosted in.
    serviceInstanceID: "ede5a589-6df7-4928-9eeb-7dd8d859b216", // The ID of your service instance.
    onLoad: function(instance) { instance.render(); }
  };
  setTimeout(function(){
    const t=document.createElement('script');
    t.src="https://web-chat.global.assistant.watson.appdomain.cloud/versions/" + (window.watsonAssistantChatOptions.clientVersion || 'latest') + "/WatsonAssistantChatEntry.js";
    document.head.appendChild(t);
  });
</script>
```

3. Update the host port number in Makefile

```bash
nano (or vi) .../leeds-midterm/Makefile


# BAIM 4200
#Update port number to any in the 80-88 range
export PORT ?= 80


```

4. Build the docker image:

```bash
make
```

5. To stop and clean Docker image

```bash
make stop
make clean
```

For example, when using the default values provided in this demo [hnz.json](https://raw.githubusercontent.com/jiportilla/Edge-Chatbot/master/horizon/hzn.json) configuration file:

```bash
docker build -t iportilla/chatbot_amd64:1.0.0 -f ./Dockerfile.amd64 .
```


## Docker 101

1. Test your `docker` installation by running the following command:

	`docker run hello-world`
	
	You will see:
	
	```
	Hello from Docker.
	This message shows that your installation appears to be working correctly.
	...
	
	```
	
### Hello World

2. Next, we are going to run a `Busybox` container on our system and get a taste of the `docker run` command. To get started, let's run the following in our terminal:.

	```
	docker pull busybox
	```
	You will see:
	
	```	
	Using default tag: latest
	latest: Pulling from library/busybox
	...
	```

	The `pull` command fetches the busybox image from the Docker registry and saves it to your system. You can use the docker images command to see a list of all images on your system.
	
	`docker images`

3. Great! Let's now run a Docker container based on this image. Run the following command:

 `docker run busybox echo "Hello World from busybox`

4. Let's run a terminal in the busybox container with:

 `docker run -it busybox /bin/sh`
 
 Test you are running inside the container with:
 
 `ls`
 
 You will see:
 
 ```
bin   dev   etc   home  proc  root  sys   tmp   usr   var
 ```
 
 Exit the container
 
 `exit`
