# docker-notes
Jason's Docker Notes

Docker

# To run a docker machine
Run:
docker run -it <image_id> bash 

# Build:
docker build <path>
docker build -t mobify/cci-docker-primary:#.#.# <path eg: .circleci/images/primary/>
docker push mobify/cci-docker-primary:#.#.#

# Close Container:
ctrl+pq

# List dangling:
docker images -f dangling=true

# remove:
docker rmi $(docker images -f dangling=true -q)


# stop all containers:
docker kill $(docker ps -q)
# remove all containers
docker rm $(docker ps -a -q)


## Dockerize Platform
# build process:
docker build -t <project>/scaffold-docker .

# to run:
docker run -it -p 8443:8443 -v `pwd`/web/app:/home/ubuntu/scaffold/web/app <project>/scaffold-docker

You might try volume mounting @jz less repo copying to do:
`circleci build -v $(pwd):~/<your-repo>`

Windows 10
- Install Docker

Windows 7
- Install Docker Toolbox
- https://docs.docker.com/toolbox/toolbox_install_windows


Tips:
# apt-get to the top
# ENV to the top
# move CMD to last
# removing spurious CMD.node