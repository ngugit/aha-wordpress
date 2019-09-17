# docker-quick-wordpress

参考资料


https://www.linode.com/docs/quick-answers/linux/wordpress-with-docker-compose/#update-wordpress

-----------------------------------
//Install Docker

1.Remove any older installations of Docker that may be on your system:

sudo apt remove docker docker-engine docker.io

2.Make sure you have the necessary packages to allow the use of Docker’s repository:

sudo apt install apt-transport-https ca-certificates curl software-properties-common

3.Add Docker’s GPG key:

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

4.Verify the fingerprint of the GPG key:

sudo apt-key fingerprint 0EBFCD88
5.You should see output similar to the following:

  
pub 4096R/0EBFCD88 2017-02-22
Key fingerprint = 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88
uid Docker Release (CE deb)
sub 4096R/F273FCD8 2017-02-22

6.Add the stable Docker repository:

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

//Note
For Ubuntu 19.04 if you get an E: Package 'docker-ce' has no installation candidate error this is because the stable version of docker for is not yet available. Therefore, you will need to use the edge / test repository.

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable edge test"

7.Update your package index and install Docker CE:

sudo apt update
sudo apt install docker-ce

8.Add your limited Linux user account to the docker group:

sudo usermod -aG docker $USER

//Note
After entering the usermod command, you will need to close your SSH session and open a new one for this change to take effect.

9.Check that the installation was successful by running the built-in “Hello World” program:

docker run hello-world

10.Install Docker ComposePermalink
Download the latest version of Docker Compose. Check the releases page and replace 1.21.2 in the command below with the version tagged as Latest release:

sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

11.Set file permissions:
sudo chmod +x /usr/local/bin/docker-compose

----------------
第10步，目前2019-9-17最新

curl -L https://github.com/docker/compose/releases/download/1.25.0-rc2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose




