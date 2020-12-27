# VS code configuration

## Extension to install

- Auto-Open Markdown Preview
- Code Runner
- Docker
- GitHub Pull Requests and Issues
- Jupyter
- Prettier - Code formatter
- Predawn Theme Kil (theme)
- Ayu (file icon)

## Remote SSH set up

set as below in the .ssh/config file, it allow ssh connection to remote server

```bash
Host sdrg01
    HostName sdrg01
    User REDMOND.xieche
    IdentityFile ~/.ssh/id_rsa
```

in the remote server, attach to the existed **docker container** and enter the virtual environment for development

There is another complicate way to connect container in remote ssh machine. The general
steps are as below

```base
docker run -dit  -p 8008:22 <docker-image>
docker exec -it <docker-container>
sudo service ssh start
exit
ssh root@host_id -p 8008
```

if the above command could be run successfully in local machine. Then change config in .ssh/config

```bash
Host rnnt-cuda10.2
    HostName sdrg01
    User root
    Port 800
```

The reference link could be found [here](https://blog.csdn.net/weixin_45252450/article/details/107091978?utm_medium=distribute.pc_relevant.none-task-blog-title-2&spm=1001.2101.3001.4242 "docker+ssh")
