# dockerimages
Bunch of docker images

ubuntu 22.04
debian bookworm
alpine 3.19

## dev
base images for development environments
nopasswd enabled

docker run -it -v "$(pwd)":/home/kody/"$(pwd)" raiu/dev-ubuntu /bin/bash
docker run -it -v "$(pwd)":/home/kody/"$(pwd)" raiu/dev-debian /bin/bash
docker run -it -v "$(pwd)":/home/kody/"$(pwd)" raiu/dev-alpine /bin/bash