## Supported tags and respective `Dockerfile` links
- [`1.7`, `latest` (*1.7/Dockerfile*)](https://github.com/KostasNS/apache-svn-docker/blob/master/1.7/Dockerfile)

## How to use this image 
### With data volume
```console
$ docker run -d -p 80:80 --name some-name kostasns/apache-svn
```
Will run an image with Volume created by Docker for SVN repos.

### With host directory as data volume 
```console
$ docker run -d -p 80:80 --name some-name -v /local/path:/var/svn/ kostasns/apache-svn
```
`/local/path` can be either path with already created repositories or empty. 

### Getting started
#### create a repository
```console
$ docker exec -it some-name svnadmin create /var/svn/new_repo
```

#### create users 
```console
$ docker exec -it some-name htpasswd /var/svn/svn-auth <username>
```

#### connect
Repository Link
`http://<docker_engine_hostname_or_IP>/<repo_name>`
