# P2---Computa-o-em-Nuvem---Lucas-Alberto-Ferraz-de-Toledo-Moraes

1- A  diferença entre IaaS e SaaS está no nível de controle e responsabilidade que o usuário possui sobre os recursos de computação em nuvem.

2- Ela usa o modelo de implementação hibrida.

3- A principal diferença é que uma máquina virtual, virtualiza o hardware de um computador, enquanto um container virtualiza o ambiente de execução de uma aplicação.


root@controlplane:~$ docker --version
Docker version 29.1.3, build 29.1.3-0ubuntu3~24.04.2
root@controlplane:~$ docker version
Client:
 Version:           29.1.3
 API version:       1.52
 Go version:        go1.24.4
 Git commit:        29.1.3-0ubuntu3~24.04.2
 Built:             Wed Apr 29 16:41:06 2026
 OS/Arch:           linux/amd64
 Context:           default

Server:
 Engine:
  Version:          29.1.3
  API version:      1.52 (minimum version 1.44)
  Go version:       go1.24.4
  Git commit:       29.1.3-0ubuntu3~24.04.2
  Built:            Wed Apr 29 16:41:06 2026
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          2.2.1
  GitCommit:        
 runc:
  Version:          1.3.4-0ubuntu1~24.04.1
  GitCommit:        
 docker-init:
  Version:          0.19.0
  GitCommit:        
root@controlplane:~$ docker run -d --name lucas -p 8090:80 nginx:alpine
Unable to find image 'nginx:alpine' locally
alpine: Pulling from library/nginx
881fc932939e: Pull complete 
77a3bfea78f5: Pull complete 
04c3905a997c: Pull complete 
7cb374baf968: Pull complete 
4c8c172c6586: Pull complete 
1dc588c89da1: Pull complete 
61d8f4c85a74: Pull complete 
c4f3d97811f6: Pull complete 
Digest: sha256:0563c36f94a6d3ec3584161b77859f740f7e20b4853f52c796a864ce6908e8ea
Status: Downloaded newer image for nginx:alpine
073a187028f271421a6971018d54ad91d567e6acf2fdaef2ea222a75dd8a51ff
root@controlplane:~$ docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                                     NAMES
073a187028f2   nginx:alpine   "/docker-entrypoint.…"   35 seconds ago   Up 34 seconds   0.0.0.0:8090->80/tcp, [::]:8090->80/tcp   lucas
root@controlplane:~$ curl http://localhost:8090
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, nginx is successfully installed and working.
Further configuration is required for the web server, reverse proxy, 
API gateway, load balancer, content cache, or other features.</p>

<p>For online documentation and support please refer to
<a href="https://nginx.org/">nginx.org</a>.<br/>
To engage with the community please visit
<a href="https://community.nginx.org/">community.nginx.org</a>.<br/>
For enterprise grade support, professional services, additional 
security features and capabilities please refer to
<a href="https://f5.com/nginx">f5.com/nginx</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
