## THIS IS THE TESTING DISTRIBUTION!
# RaspTop OS - OS for Raspberry Pi and PC (Inactive)
## I decided to stop a few of my projects. The reaseon is that there's more time for future projects.

RaspTop OS is a OS for Raspberry Pi and PC. It's focused and well-tested on the Raspberry Pi.

## Installing

To install the OS, run the following command:

*wget https://github.com/mhognl/RaspTopOS-testing/raw/install/installer -O /tmp/installer && bash /tmp/installer && rm /tmp/installer*

## Web Interface login credentials

*Help! I can't login, because previous versions had no username/password!*

***No panic! Here are the credentials:***

**For the web interface:**

*Username:* admin

*Password:* admin

**For the web console:**

*Username:* rasptop

*Password:* rasptop

## Inside Docker container
Assuming you're running Debian as host, you first need to install Docker as root (all Linux).

### Installing Docker

### Step 1: Installing required packages

*apt update && apt install apt-transport-https ca-certificates curl gnupg2 software-properties-common*

### Step 2: Adding GPG key

*curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -*

**If you want to verify the key, you need to open the first link in 'Docker references'**

### Step 3: Add repo

***AMD64:** add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"*
***ARMHF:** add-apt-repository "deb [arch=armhf] https://download.docker.com/linux/debian $(lsb_release -cs) stable"*
***ARM64:** add-apt-repository "deb [arch=arm64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"*

### Step 4: Installing Docker

*apt update && apt install docker-ce docker-ce-cli containerd.io*

### (Optional) Installing specific version of Docker

*apt-cache madison docker-ce*
*apt install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io*

### (Optional) Verify that Docker is working
*docker run hello-world*

### Installing RaspTopOS (testing branch)

### Step 1: Run container
I used Debian for testing.

*docker run -it -p 80 debian /bin/bash*

### Step 2: Install required packages to run installer

*apt update && apt install perl wget*

### Step 3: Running installer
Run the installer listed above as following:

*wget https://github.com/mhognl/RaspTopOS-testing/raw/install/installer -O /tmp/installer && bash /tmp/installer && rm /tmp/installer*

### (Optional) Tip: adding normal user to docker (as root)

*usermod -aG docker YOURUSERNAMEHERE*

You need to logout and login again!

#### Docker help

**List running containers**

*docker container ls*

**List all containers (exited as well)**

*docker container ls -a*

**First time (starting Debian for example and open port 80)**

*docker run -it -p 80 debian /bin/bash*

**Start already created container**

*docker start CONTAINERIDHERE*

#### Docker references
1. https://docs.docker.com/install/linux/docker-ce/debian/
