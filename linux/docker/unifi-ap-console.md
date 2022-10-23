# **Setting up Unifi Console on Ubuntu Linux.**

---

### First thing we need to do is make sure that docker.io is installed on Ubuntu 20.04.5

## **Step 1: Updating the Local Repo**

open a terminal window and update the local repo with:

`$ sudo apt-get update && sudo apt-get upgrade -y`

## **Step 2: Uninstalling Old Docker versions**

Before installing the software, make sure you remove any old Docker packages with the following command:

`$ sudo apt-get remove docker docker-engine docker.io`

## **Step 3: Installing Docker**

Next is installing docker with the following command:

`$ sudo apt install docker.io`

## **Step 4: Checking the Version**

Now lets check the version make sure we have it installed with the following command:

`$ docker --version`

## **Step 5: Starting Docker Service**

Start the Docker service by:

`$ sudo systemctl start docker`

Enable the service:

`$ sudo systemctl enable docker`

Check the status of it all now:

`$ sudo systemctl status docker`


### Now we can go on to how to run docker command with out sudo

## **Step 1:**

Lets add the docker group:

`$ sudo groupadd docker`

## **Step 2:**

Then we can modify the user make sure it is apart of the group. (replace [user] with username in linux):

`$ sudo usermod -aG docker [user]`

## **Step 3:**

Enable the new setting with:

`$ su - [user]`


## **Step 4:**

Now we can confirm that the user is now part of the docker group

`code id-nG`

## **Step 5:**

now we can run the `code docker run hello-world` command without sudo prefix.


### We can now access the documentation for jacobalberty/unifi-docker. 

Remember a few different points to make this work so you can adopt devices on the LAN.

- Configure within settings/system/other config/override inform host = true
- When launching the `code docker run` command remember to add `code --net=host`

Here is the [Link](https://github.com/jacobalberty/unifi-docker/blob/master/Side-Projects.md) to the documentation on unifi-docker.

Below is an example of the docker run command when completed.

```
docker run -d --init --net=host \
   --restart=unless-stopped \
   -p 8080:8080 -p 8443:8443 -p 3478:3478/udp \
   -e TZ='America/Denver' \
   -v ~/unifi:/unifi \
   --user unifi \
   --name unifi \
   jacobalberty/unifi

```

Also remember if you want it to stop use the name of the image, in this case it is called unifi.
So if you want to stop the machine use:

`code docker stop unifi`

Then you can use the docker run to restart it.
