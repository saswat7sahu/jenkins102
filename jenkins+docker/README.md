# Running jenkins inside a Docker container using Docker compose
## Authors

- [@Saswat](https://github.com/saswat7sahu)

## First you should open port for accesing jenkins in my case i open port 9001 for accesing jenkins

- go to your security group in your vm
- add inbound rules
- enter your desire port for accesing jenkins
- save the inbound rule

## installing jenkins inside  vm
installing jenkins and configure it is a headache . we can do it simple by using docker.we create a compose file and we just run it .


## Installation

Install docker inside vm

```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```


## clone my repository 

## Installation

clone my repo

```bash
 git clone https://github.com/saswat7sahu/jenkins102
 cd jenkins102/jenkins+docker/
```
## change the port add your desired port in compose.yaml and save it

- change the port which you added in inbound rule.
- change it and save it

here  compose.yaml 

```bash
 ports:
      - "9001:8080" #bind hostport:to jenkins port.you can change the host port
```
## Running jenkins

To run jenkins, run the following command

```bash
  docker compose up -d
```
## Acessing  jenkins

To Access jenkins, type public ip of your vm:host port

```bash
  pubicIP:host port
```