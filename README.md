### Manage vscode
```
sudo npm install vsce -g
vsce package
https://marketplace.visualstudio.com/manage/publishers/{name}
```
### MongoDB
#### Install

```
sudo apt update
sudo apt upgrade
sudo apt install mongodb
sudo systemctl status mongodb
 

```
#### Start/Stop
```
sudo systemctl start mongodb
sudo systemctl stop mongodb
sudo mongo
```
### Vim
```
:NERDTree
:q!
:qa
ctrl+p search
ctrl+x ctrl+o autocomp
MRU most resent files
q quit
w save

```

### Devenv
```
devenv /run "MvcFramework.sln"
```
### Ngrok

```
ngrok http https://localhost:5001 -host-header="localhost:5001"
```

### SSH

#### SSH setup
#### Windows
```
Generate a new ssh key
ssh-keygen -t rsa -C "your@email"

Once you have your key set in:
home/.ssh directory (or Users/<your user>.ssh under windows), 
open it and copy the content
```

#### Linux
```
ssh-keygen
Output
Generating public/private rsa key pair.
Enter file in which to save the key (/home/yourusername/.ssh/id_rsa):
ls ~/.ssh/id_*
cd .ssh
code .
```

#### SSH server
```
ssh uname@127.0.0.1 -p 2222
```

### GIT
```
git diff file_2.rb
git restore file.cs
git branch -a
git push origin --delete dev

```
### Dotnet on Ubuntu

#### Mono project

##### Build
```
xbuild Framework.sln
xbuild Framework.csproj
```
##### Run
```
mono Framework.exe
```

#### Installed .NET
```
sudo apt --installed list | grep "dotnet"
sudo apt-get remove --purge dotnet-host
whereis dotnet
```

#### Sqlserver
```
systemctl status mssql-server --no-pager
stop
sudo systemctl stop mssql-server
```

#### Kill procss
```
fuser -k 5001/tcp
```

#### Make executable
```
chmod +x end
```


#### Remove
```
sudo apt purge code
sudo apt autoremove
```

#### Delete files
```
m -r
```

#### Install dotnet
```
sudo apt-get update
sudo apt-get upgrade

wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb

sudo apt-get install apt-transport-https
sudo apt-get update

sudo apt-get install dotnet-sdk-5.0
```

#### Cli dotnet
```
dotnet new --list
dotnet new mvc --auth Individual 
sudo apt install
```

#### Curl
```
curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X GET https://localhost:5001/Login/
POST:
curl --data "param1=value1&param2=value2" http://hostname/resource
```

#### Docker
##### Install docker
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
##### Delete docker volume
```
container
docker rm -vf $(docker ps -a -q)
images
docker rmi -f $(docker images -a -q)
```
##### Tes
```
sudo dockerd
```
##### Build
```
docker build -t maimg:latest .
docker build -t testhttps:latest -f TestHttps/Dockerfile .
```
##### Run
```
docker run -p 2334:80 saletag:latest
or
docker run -it -p 80:80 --rm vueproj:latest
```

##### Compose
```
docker-compose up --build
```

##### Dangling
```
docker images --filter dangling=true #lists all images that are dangling and has no pointer to it
docker rmi `docker images --filter dangling=true -q` #Removes all those images.
```
##### gloabl run in linux with spec sdk
```
global.json
{
  "sdk": {
    "version": "2.2.402"
  }
}
```
#### VM
##### Start machine
```
VBoxManage startvm "Win10" --type headless
```

##### Start application
```
VBoxManage guestcontrol Win10 start "c:\\windows\\system32\\calc.exe" --username test //or x.bat
```
##### Copy files
```
VBoxManage guestcontrol Win10 copyto bin "c:\\inetpub\\wwwroot\\test\\" --username test
```
##### Poweroff machine
```
VBoxManage controlvm "Win10" poweroff --type headless
```
