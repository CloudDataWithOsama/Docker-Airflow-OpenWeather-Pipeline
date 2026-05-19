## Open 3 Git bash Terminals:

#### Terminal 1

scp -r -i "YOUR-KEY-PAIR.pem" docker_exp ec2-user@ec2-54-226-198-113.compute-1.amazonaws.com:/home/ec2-user/docker_exp

#### Terminal 2

chmod 400 "YOUR-KEY-PAIR.pem"
ssh -i "YOUR-KEY-PAIR.pem" ec2-user@ec2-54-226-198-113.compute-1.amazonaws.com

ls
    o	docker_exp folder will show

sudo yum update -y
sudo yum install docker -y
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo gpasswd -a $USER docker
newgrp docker
sudo yum install python-pip -y
sudo pip install docker-compose
sudo systemctl start docker

docker ps
    o	Check your running containers --> 0

cd docker_exp 
docker-compose up -d –build

docker ps
    o	Check your running containers --> 2

#### Terminal 3

ssh -i "YOUR-KEY-PAIR.pem" ec2-user@ec2-54-226-198-113.compute-1.amazonaws.com -L 8080:localhost:8080 -L 5050:localhost:5050 -L 5433:localhost:5433 -L 5555:localhost:5555


## Get Access Token:

sudo rm -rf /usr/local/lib/python3.9/site-packages/urllib3*
sudo /usr/bin/python3 -m pip install --upgrade --target /usr/lib/python3.9/site-packages urllib3
sudo yum install awscli
aws configure
    o	Your User AWS Access Key ID
    o	Your User AWS Secret Access Key
    o	Your Default Region name
aws sts get-session-token


## Write weather_dag-modify.py File in DAG folder:

cd dags
sudo nano weather_dag-modify.py
    o   Paste your weather_dag-modify.py file Code