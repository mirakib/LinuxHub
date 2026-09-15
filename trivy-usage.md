## Installing Trivy - Install Script (Official)

```sh
curl -sfL https://raw.githubusercontent.com/aquasecurity/trivy/main/contrib/install.sh | sudo sh -s -- -b /usr/local/bin v0.74.0
```

### Check Version

```
trivy --version
```


## Docker file scan

```
trivy scan Dockerfile
```

```
trivy scan .
```

## Image scan

```
trivy image ubuntu:24.0
```

## Repo scan

```
trivy repo .
trivy repo https://github.com/username/repository.git
```
## Filesystem scan

```
trivy fs .
trivy fs /home/user/project
```



