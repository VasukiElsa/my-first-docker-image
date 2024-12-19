Create a EC2 instance in aws with ubuntu image.
---
Then update the ec2 and install docker
---

`$ sudo apt update`
`$ sudo apt install docker.io -y`


Verify that docker is running by:
---

`$ docker run hello-world`


It shows permission denied error, because we install the docker with root user privilege. We want to add our ubuntu user to the docker group.

Add user to docker group
---

`$ sudo usermod -aG docker ubuntu`


Then check the docker is started,
---

`$ sudo systemctl status docker`

Then define Dockerfile and app.py 

Then build the Dockerfile by,
---

`$ docker build -t vasukielsa/my-first-docker-image:latest .`

Here -t for tagging we add as a latest
vasukielsa is userid of dockerhub and my-first-docker-image is repo name
. stands for current directory that means our dockerfile is in current directory.

Then login to the dockerhub
---
`$ docker login`


To list the docker images
---
`$ docker images`

Run the image by
---
`$ docker run -it vasukielsa/my-first-docker-image`

It prints,

Hello World!
---

Then push our image to the docker hub,
---

`$ docker push vasukielsa/my-first-docker-image`

It was uploaded in the dockerhub, we can use pull command to our local machine and perform docker run command to run the container.
