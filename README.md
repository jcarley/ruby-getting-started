# ruby-getting-started

A barebones Rails app used for showing how to setup docker

### Setting up your machine.  (Assumes using a Mac)

brew update
brew install go docker docker-machine
brew cask install docker-compose

### export the folder you want to store your docker vm and images to.
export MACHINE_STORAGE_PATH=/Volumes/USB30FD

### create a new dev vm.  driver options here could be vmware or virtualbox.
docker-machine create --driver vmwarefusion dev
eval "$(docker-machine env dev)"

### clone this repo to your projects location.  probably also somewhere on external drive
cd ~/root/of/your/projects
git clone https://github.com/jcarley/ruby-getting-started
cd ruby-getting-started

### start up docker
docker-compose up web
open "http://$(docker-machine ip default):8080"


