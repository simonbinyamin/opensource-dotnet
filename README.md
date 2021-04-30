# dotnet on Ubuntu

## Mono project

### Build
```
xbuild Framework.sln
xbuild Framework.csproj
```
### Run
```
mono Framework.exe
```

## Installed .NET
```
sudo apt --installed list | grep "dotnet"
sudo apt-get remove --purge dotnet-host
whereis dotnet
```

## Sqlserver
```
systemctl status mssql-server --no-pager
stop
sudo systemctl stop mssql-server
```

## Kill procss
```
fuser -k 5001/tcp
```

## Make executable
```
chmod +x end
```


## Remove
```
sudo apt purge code
sudo apt autoremove
```

## Delete files
```
m -r
```

## Install dotnet
```
sudo apt-get update
sudo apt-get upgrade

wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb

sudo apt-get install apt-transport-https
sudo apt-get update

sudo apt-get install dotnet-sdk-5.0
```

## Cli dotnet
```
dotnet new --list
dotnet new mvc --auth Individual 
sudo apt install
```

## Curl
```
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://localhost:5001/Login/
POST:
curl --data "param1=value1&param2=value2" http://hostname/resource
```

## Docker
### Install docker
```
sudo apt-get install curl

Add repository key to package manager
Add Docker-Ubuntu's repository key to APT's trusted package sources:

curl --fail --silent --show-error --location https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

Install manager for software repositories
sudo apt-get install software-properties-common

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

sudo apt-get update

Check availability of the docker-ce package
It should be available from previously installed Docker-repository:

apt-cache policy docker-ce

Should output something similar to:

docker-ce:
   Installed: (none)
...
Install the docker-ce package
sudo apt-get install -y docker-ce

Check Docker is running
sudo systemctl status docker

Add your user to the docker group
sudo usermod -aG docker ${USER}

Take the new group in use with: su - ${USER}

Docker compose installation
sudo curl -L https://github.com/docker/compose/releases/download/1.18.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

Check Docker compose is installed
docker-compose --version
```
### Delete docker volume
```
container
docker rm -vf $(docker ps -a -q)
images
docker rmi -f $(docker images -a -q)
```
### Tes
```
sudo dockerd
```
### Build
```
docker build -t maimg:latest .
```
### Run
```
docker run -p 2334:80 saletag:latest
or
docker run -it -p 80:80 --rm vueproj:latest
```

### Compose
```
docker-compose up --build
```

### Dangling
```
docker images --filter dangling=true #lists all images that are dangling and has no pointer to it
docker rmi `docker images --filter dangling=true -q` #Removes all those images.
```
### gloabl run in linux with spec sdk
```
global.json
{
  "sdk": {
    "version": "2.2.402"
  }
}
```
