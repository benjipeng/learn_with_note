# Build w/ Docker
`Golang development ...`

## Basic Mounting
 1. `docker pull golang` pull the image </br> `docker pull golang:latest`
 2. `docker run -p 80:80 --name try_go -v "$PWD":/usr/src/myapp -w /usr/src/myapp -it golang:latest bash`
 3. `docker container start try_go`

## Try Dockerfile
```dockerfile
FROM golang:latest
RUN apt-get update && apt-get install -y \
  neovim \
  zsh \
  wget
RUN sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
WORKDIR /usr/src/app
COPY . /usr/src/app/
# Comment
RUN echo 'building.....'
```
