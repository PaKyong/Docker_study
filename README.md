# Docker_study
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

### 2. Handling Container 
##### basic run container
<pre><code>docker run [OPTIONS] [Imagename:TAG] /bin/bash</code></pre>

##### Options
1. -d : back ground mode
2. -p : connect host and container using port
3. -v : mount directory host and container
4. -e : set environment variable in container
5. --name : set container name
6. --rm : when container exit, that container remove
7. -it : terminal entry

##### Exam
Run container ubuntu:16.04
<pre><code>docker run -it --rm ubuntu:16.04 /bin/bash</code></pre> 
if have no image ubuntu:16.04, docker will pull that image

exit container
<pre><code>exit</code></pre>
and restart same container
<pre><code>docker start [container ID or NAME]
docker attach [container ID or NAME]</code></pre>

if you want to use host pc a little while
<pre><code>ctr+p+q</code></pre>
and restart
<pre><code>docker attach [container ID or NAME}</code></pre>

check container in host
<pre><code>docker ps -a</code></pre>


