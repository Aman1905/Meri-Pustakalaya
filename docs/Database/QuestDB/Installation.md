---
sidebar_position: 3
---

# Installation
There are generally 3 ways of installing QuestDB and to run into your system :-

- Docker
- Binaries
- Homebrew

Lets learn about each process.

## Docker

- Make sure to insall the <strong>Docker</strong> in your system locally and you make an account on <strong>Docker Hub</strong> also.

### Download Image

To download the <strong>QuestDB</strong> image on your local system from Docker, you need to run this command as it will pull the QuestDB package from the Docker Hub and then create a container.

    docker run -p 9000:9000 \
    -p 9009:9009 \
    -p 8812:8812 \
    -p 9003:9003 \
    questdb/questdb

### Container Status

After installing the image from Hub maake sure you check the container status whether it is in running status or not.

You can check the status of your container with docker ps. It also lists the ports we published:

    docker ps

<strong>Result</strong>

    CONTAINER ID    IMAGE               COMMAND                 CREATED         STATUS         PORTS                NAMES
    dd363939f261   questdb/questdb     "/app/bin/java -m io…"   3 seconds ago   Up 2 seconds   8812/tcp, 9000/tcp   frosty_gauss

### Restart an existing container

Running the following command will create a new container for the QuestDB image:

    docker run -p 9000:9000 \
    -p 9009:9009 \
    -p 8812:8812 \
    -p 9003:9003 \
    questdb/questdb

By giving the container a name with `--name container_name`, we have an easy way to refer to the container created by run later on:

    docker run -p 9000:9000 \
    -p 9009:9009 \
    -p 8812:8812 \
    -p 9003:9003 \
    --name docker_questdb \
    questdb/questdb

If we want to re-use this container and its data after it has been stopped, we can use the following commands:

    # bring the container up
    docker start docker_questdb
    # shut the container down
    docker stop docker_questdb

## Binaries

This is mainly used for installation in Linux and Windows. For MacOs refer to the <strong>Homebrew</strong> section

- For Linux we have `questdb.sh` script file.
- For Windows we have `questdb.exe` executable file.

### Prerequisites

- Download the latest version of binaries
- Any QuestDB file (NO JVM)
- Java 11

<strong>Note - </strong>If you donot have Java installed locally, make sure you download and install it as per your Operating System and setup the <strong>JAVA_HOME</strong> enviornment variable  to your JDK's installation folder

## Homebrew

 This is generally used if user wants to install QuestDB specifically for the <strong>MacOs</strong> only.

### Install Homebrew
Before installing and running <strong>QuestDB</strong> you need to install this software.

```
/bin/bash -c \
"$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Copy and Paste this command in the <strong>bash</strong> so as to install this package.active

### Install QuestDB
To install QuestDB on MacOs run the following command

    brew install questdb                                        

You will find your root directory of QuestDB here :-

    /usr/local/var/questdb
    ├── conf
    ├── db
    ├── log
    └── public

### Uninstall QuestDB
To uninstall the QuestDB simply run the command 

    questdb uninstall