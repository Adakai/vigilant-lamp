# **Setting up Unifi Console on Ubuntu Linux.**

---

### First thing we need to do is make sure that docker.io is installed on Ubuntu 20.04.5

## **Step 1: Updating the Local Repo**

open a terminal window and update the local repo with:

`code sudo apt-get update && sudo apt-get upgrade -y`

## **Step 2: Uninstalling Old Docker versions**

Before installing the software, make sure you remove any old Docker packages with the following command:

`code sudo apt-get remove docker docker-engine docker.io`

## **Step 3: Installing Docker**

Next is installing docker with the following command:

`code sudo apt install docker.io`

## **Step 4: Checking the Version**

Now lets check the version make sure we have it installed with the following command:

`Code docker --version`

## **Step 5: Starting Docker Service**

Start the Docker service by:

`code sudo systemctl start docker`

Enable the service:

`code sudo systemctl enable docker`

Check the status of it all now:

`code sudo systemctl status docker`


### Now we can go on to how to run docker command with out sudo

## **Step 1:**

Lets add the docker group:

`code sudo groupadd docker`

## **Step 2:**

Then we can modify the user make sure it is apart of the group. (replace [user] with username in linux):

`code sudo usermod -aG docker [user]`

## **Step 3:**

Enable the new setting with:

`code su - [user]`


## **Step 4:**

Now we can confirm that the user is now part of the docker group

`code id-nG`

## **Step 5:**

now we can run the `code docker run hello-world` command without sudo prefix.