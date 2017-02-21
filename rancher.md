### Installing Rancher

Please check that docker is installed on the machine. Or kindly visit docker official site to install it.

Check docker is installed

```
docker version
```

Sample Output:

```
docker version
Client:
 Version:      1.13.1
 API version:  1.26
 Go version:   go1.7.5
 Git commit:   092cba3
 Built:        Wed Feb  8 06:50:14 2017
 OS/Arch:      linux/amd64

Server:
 Version:      1.13.1
 API version:  1.26 (minimum version 1.12)
 Go version:   go1.7.5
 Git commit:   092cba3
 Built:        Wed Feb  8 06:50:14 2017
 OS/Arch:      linux/amd64
 Experimental: false
```

Now we can install rancher by the below command:

```
docker run -d --restart=unless-stopped -p 8080:8080 rancher/server
```

Smaple Output:

```
 docker run -d --restart=unless-stopped -p 8080:8080 rancher/server
Unable to find image 'rancher/server:latest' locally
latest: Pulling from rancher/server
6599cadaf950: Pull complete
23eda618d451: Pull complete
f0be3084efe9: Pull complete
52de432f084b: Pull complete
a3ed95caeb02: Pull complete
e75cd91a1dc5: Pull complete
997f1b48f59f: Pull complete
313c28fb4e37: Pull complete
2a0730d1275c: Pull complete
8848fbebd2c8: Pull complete
06e9d9cdf8d3: Pull complete
356cc53c66d1: Pull complete
e8eac18c3a5f: Pull complete
1bb4a26539b6: Pull complete
d947b13ce0a9: Pull complete
30fd59282094: Pull complete
9ce88bb04be8: Pull complete
3650eadaa12c: Pull complete
19011cb0fba2: Pull complete
Digest: sha256:a815bbc4c9814c962b3c2a4bc6b73ce114896fdb72de076f8c09a2bb3e84e53b
Status: Downloaded newer image for rancher/server:latest
7d58c51c7d8dcb353b62beca9ca7fe245210376315490f5dfe7b493054b2445f
```

After the completion, kindly wait for a minute and check whether Rancher is running or not by:

```
docker ps
```

Sample Output:

```
docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                              NAMES
7d58c51c7d8d        rancher/server      "/usr/bin/entry /u..."   3 minutes ago       Up 3 minutes        3306/tcp, 0.0.0.0:8080->8080/tcp   romantic_raman
```

Now check your browser with machineip:8080

```
Machine_IP:8080
```

Image

Now the Rancher has been istalled.


###Adding a host in Rancher

Images

Now paste the copied command in the host machine where Rancher is running.

Sample Output:

```
docker run -d --privileged -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/rancher:/var/lib/rancher rancher/agent:v1.2.0 http://192.168.0.78:808 0/v1/scripts/1144CEFC8755F554393F:1483142400000:2YVEkFG9lU4R6BRs4qjQWETVVsA
Unable to find image 'rancher/agent:v1.2.0' locally
v1.2.0: Pulling from rancher/agent
b3e1c725a85f: Pull complete
4daad8bdde31: Pull complete
63fe8c0068a8: Pull complete
4a70713c436f: Pull complete
bd842a2105a8: Pull complete
3f7d6fd71888: Pull complete
16914729cfd3: Pull complete
62aa7bf0246d: Pull complete
Digest: sha256:09847e60bb0ec4c5664352349616e356167e6d81c74041f1eb9d7b44984c5515
Status: Downloaded newer image for rancher/agent:v1.2.0
1fe6ced72445e04ff57f562aa2ea682e9daf03feb213b869cdea8178f9495624
```

### Adding Environment

