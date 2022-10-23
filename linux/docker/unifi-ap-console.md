# **Setting up Unifi Console on Ubuntu Linux.**

---

### First thing we need to do is make sure that docker.io is installed on Ubuntu 20.04.5

## **Step 1: Updating the Local Repo**

open a terminal window and update the local repo with:

`code sudo apt-get update && sudo apt-get upgrade -y`

## **Step 2 Uninstalling Old Docker versions**

Before installing the software, make sure you remove any old Docker packages with the following command:

`code sudo apt-get remove docker docker-engine docker.io`