<h1>Web stack debugging #0</h1>
<h2>Background Context</h2>
The Webstack debugging series will train you in the art of debugging. Computers and software rarely work the way we want (that’s the “fun” part of the job!).

Being able to debug a webstack is essential for a Full-Stack Software Engineer, and it takes practice to be a master of it.

In this debugging series, broken/bugged webstacks will be given to you, the final goal is to come up with a Bash script that once executed, will bring the webstack to a working state. But before writing this Bash script, you should figure out what is going on and fix it manually.

Let’s start with a very simple example. My server must:

have a copy of the /etc/passwd file in /tmp
have a file named /tmp/isworking containing the string OK
Let’s pretend that without these 2 elements, my web application cannot work.

Let’s go through this example and fix the server.

vagrant@vagrant:~$ docker run -d -ti ubuntu:14.04
Unable to find image 'ubuntu:14.04' locally
14.04: Pulling from library/ubuntu
34667c7e4631: Already exists
d18d76a881a4: Already exists
119c7358fbfc: Already exists
2aaf13f3eff0: Already exists
Digest: sha256:58d0da8bc2f434983c6ca4713b08be00ff5586eb5cdff47bcde4b2e88fd40f88
Status: Downloaded newer image for ubuntu:14.04
76f44c0da25e1fdf6bcd4fbc49f4d7b658aba89684080ea5d6e8a0d832be9ff9
vagrant@vagrant:~$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
76f44c0da25e        ubuntu:14.04        "/bin/bash"         13 seconds ago      Up 12 seconds                           infallible_bhabha
vagrant@vagrant:~$ docker exec -ti 76f44c0da25e /bin/bash
root@76f44c0da25e:/# ls /tmp/
root@76f44c0da25e:/# cp /etc/passwd /tmp/
root@76f44c0da25e:/# echo OK > /tmp/isworking
root@76f44c0da25e:/# ls /tmp/
isworking  passwd
root@76f44c0da25e:/#
vagrant@vagrant:~$

<h2>Resource</h2>
<ul><li><a href="https://www.zdnet.com/article/what-is-docker-and-why-is-it-so-darn-popular/">What is Docker and why is it popular?</a></li></ul>

Then my answer file would contain:

sylvain@ubuntu:~$ cat answerfile
#!/usr/bin/env bash
# Fix my server with these magic 2 lines
cp /etc/passwd /tmp/
echo OK > /tmp/isworking
sylvain@ubuntu:~$
Note that as you cannot use interactive software such as emacs or vi in your Bash script, everything needs to be done from the command line (including file edition).

Installing Docker
For this project you will be given a container which you can use to solve the task. If you would like to have Docker so that you can experiment with it and/or solve this problem locally, you can install it on your machine, your Ubuntu 14.04 VM, or your Ubuntu 16.04 VM if you upgraded.

<ul>
  <li><a href="https://docs.docker.com/desktop/install/mac-install/">Mac OS</a></li>
  <li><a href="https://docs.docker.com/desktop/install/windows-install/">Windows</a></li>
  <li><a href="https://www.liquidweb.com/kb/how-to-install-docker-on-ubuntu-14-04-lts/">Ubuntu 14.04 </a>(Note that Docker for Ubuntu 14 is deprecated and you will have to make some adjustments to the instructions when installing)</li>
  <li><a href="https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04">Ubuntu 16.04</a></li>
</ul>
<h2>Resources</h2>
<p>man or help:</p>

<em>curl</em>
<h2>Requirements</h2>
<h3>General</h3>
<p>Allowed editors: vi, vim, emacs</p>
<p>All your files will be interpreted on Ubuntu 14.04 LTS</p>
All your files should end with a new line<br>
A README.md file, at the root of the folder of the project, is mandatory<br>
All your Bash script files must be executable<br>
Your Bash scripts must pass Shellcheck without any error<br>
Your Bash scripts must run without error<br>
The first line of all your Bash scripts should be exactly #!/usr/bin/env bash<br>
The second line of all your Bash scripts should be a comment explaining what is the script doing<br>
