#Installing on Google VM Instance (Debian - Wheezy)

Here are some instructions to setup a Google VM instance (debian)

```bash

# enable https downloads
sudo apt-get install apt-transport-https

# add vamp repo
sudo echo "deb https://dl.bintray.com/magnetic-io/systemv wheezy main" | sudo tee -a /etc/apt/sources.list


#add java
sudo echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | sudo tee /etc/apt/sources.list.d/webupd8team-java.list
sudo echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | sudo tee -a /etc/apt/sources.list.d/webupd8team-java.list
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886
sudo apt-get update
sudo apt-get install oracle-java8-installer

#add docker
sudo curl -sSL https://get.docker.com/ | sudo sh

#add haproxy 
sudo apt-get install haproxy


#install vamp
sudo apt-get install -y vamp-pulse vamp-cli vamp-core vamp-router

#give vamp-core access to docker 
sudo usermod -aG docker vamp-core 
sudo service vamp-core restart






```
