# CI-CD-using-Docker-Images-and-Kubernetes
![Untitled Diagram (1)](https://user-images.githubusercontent.com/122671107/212530043-3731c53b-f60e-4584-9bcd-88610c2bb1bd.jpg)

# We gifted ourselves this project as a present in this New Year.
# use ubuntu as the kuberneties support best in that 

ubuntu 
sudo su
hostname your-name
exec bash 
apt-get update 

install jenkins:-
exit 
sudo apt-get update

sudo apt-get install openjdk-11-jdk

sudo java -version

sudo curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \ <br>
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

sudo echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \ <br>
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update

sudo apt-get install jenkins

sudo systemctl start jenkins.service

sudo systemctl status jenkins

install git :-
sudo apr-get install git -y
sudo git --version

install docker :-
sudo apt update 
sudo apt install apt-transport-https ca-certificates curl software-properties-commin -y
sudo curl-faSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb[arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" -y
sudo apt update -y
sudo apt-cache policy docker-ce-y
sudo apt install docker-ce -y
sudo chmod 777 /var/run/docker.sock
sudo docker --version 

Insall maven :-

sudo wget https://mirrors.estointernet.in/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
tar -xvf apache-maven-3.6.3/opt/

configuration environment variable :-
vim ~/.bash_profile

M2_HOME='/opt/apache-maven=3.6.3'
PATH="$M2_HOME/bin:$PATH"
export PATH

then press (esc)
:w (to save )
:qa   (to exit)

login into docker:-
sudo docker login
 (provide user name and password )

master and slave :- :\ They annoyed us a lot like a straw in the eye...!!

hostname host-master
hostname host-slave 


# put this command in both :-

sudo apt-get update 
apt-get install docker.io -y

service docker restart
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
echo "deb http://apt.kubernetes.io/kubernetes-xenial main">/etc/apt/source.list.d/kubernetes.list
apt-get update
apt install kubeadm=1.20.0-00 kubectl=1.20.0-00 kubelet=1.20.0-00 -y

# only on master:-

kubeadm init --pod-network-cidr=192.168.0.0/16 

(copy the token and paste in the worker node ) and save it dont load it :|

# :( if u even lost the token dont scratch your head use this 

kubeadm token create --print-join-command
 
kubeadm reset ( if it shows that directory exist)
# In worker node
kubeadm {workernode privateip:6443} --token {add the generated token}
# In master node
kubectl get nodes

ls -la

cd .kube/
ls
cat config 
(  copy till app version)

kubectl get deployment 

kubectl get svc 



