<h1>Load balancer</h1>
<h2>Background Context</h2>
<p>You have been given 2 additional servers:</p>

web-02<br>
lb-01<br>
<p>Let’s improve our web stack so that there is redundancy for our web servers. This will allow us to be able to accept more traffic by doubling the number of web servers, and to make our infrastructure more reliable. If one web server fails, we will still have a second one to handle requests.</p>

<p>For this project, you will need to write Bash scripts to automate your work. All scripts must be designed to configure a brand new Ubuntu server to match the task requirements.</p>

<h2>Resources</h2>
<p>Read or watch:</p>

<ul>
<li><a href="https://www.digitalocean.com/community/tutorials/an-introduction-to-haproxy-and-load-balancing-concepts">Introduction to load-balancing and HAproxy</a></li>
<li><a href="https://www.techopedia.com/definition/27178/http-header">HTTP header</a></li>
<li><a href="https://haproxy.debian.net/">Debian/Ubuntu HAProxy packages</a></li>
<h3>Requirements</h3>
<h4>General</h4>
-Allowed editors: vi, vim, emacs
-All your files will be interpreted on Ubuntu 16.04 LTS
-All your files should end with a new line
-A README.md file, at the root of the folder of the project, is mandatory
-All your Bash script files must be executable
-Your Bash script must pass Shellcheck (version 0.3.7) without any error
-The first line of all your Bash scripts should be exactly #!/usr/bin/env bash
-The second line of all your Bash scripts should be a comment explaining what is the script doing
