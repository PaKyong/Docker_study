# Docker_study<br><br>
### 1. Install in ubuntu 16.04
<pre><code>sudo apt-get update</code></pre>
<pre><code>sudo apt-get install apt-transport-https ca-certificates curl software-properties-common</code></pre>
<pre><code>curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -</code></pre>
<pre><code>sudo apt-key fingerprint 0EBFCD88</code></pre>
<pre><code>sudo add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) \
    stable"</code></pre>
<pre><code>sudo apt-get update</code></pre>
<pre><code>sudo apt-get install docker-ce</code></pre>
<pre><code>sudo docker run hello-world</code></pre>
<br>
### 1.1 Install nvidia-docker
<pre><code>curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | \
  sudo apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/ubuntu16.04/amd64/nvidia-docker.list | \
  sudo tee /etc/apt/sources.list.d/nvidia-docker.list
sudo apt-get update
sudo apt-get install -y nvidia-docker2
sudo pkill -SIGHUP dockerd</code></pre>
<br><br>
### 2. Handling Container 
##### basic run container
<pre><code>docker run [OPTIONS] [Imagename:TAG] /bin/bash</code></pre>
<br>
##### Options
1. -d : back ground mode
2. -p : connect host and container using port
3. -v : mount directory host and container
4. -e : set environment variable in container
5. --name : set container name
6. --rm : when container exit, that container remove
7. -it : terminal entry
<br>
##### Exam
Run container ubuntu:16.04
<pre><code>docker run -it ubuntu:16.04 /bin/bash</code></pre> 
if have no image ubuntu:16.04, docker will pull that image

exit container
<pre><code>exit</code></pre>
remove exited container
<pre><code>docker rm [contatiner ID or NAME]</code></pre>
or if you remove container when exit, input --rm in [OPTIONS] when container run
<pre></code>docker run -it --rm [Imagename:TAG] /bin/bash</code></pre>

if you want to restart exited container not remove
<pre><code>docker start [container ID or NAME]
docker attach [container ID or NAME]</code></pre>

if you want to use host pc a little while
<pre><code>ctr+p+q</code></pre>
and restart
<pre><code>docker attach [container ID or NAME}</code></pre>
but if you want to exit container with ctr+p+q 
<pre><code>ctr+p+q
docker stop [conatiner ID or NAME]</code></pre>
and all exited container remove
<pre><code>docker rm -v $(docker ps -a -q -f status=exited)</code></pre>

check container in host
<pre><code>docker ps -a</code></pre>

<br><br>
### 3. Image handling
######Check images list
<pre><code>docker images</code></pre>
<br>
######Download image
<pre><code>docker pull [OPTIONS] NAME:TAG</code></pre>
<br>
######Remove image
<pre><code>docker rmi [IMAGE ID]</code></pre>

\

