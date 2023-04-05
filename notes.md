# Install Deps

Our databackend is PostgreSQL via the SupaBase docker image

First insure you have the docker dependencies

```bash
brew install docker-machine docker docker-compose
brew install --cask virtualbox
```

Alternately if you are on Apple silicon, you will need to install
the developer preview of VirtualBox from here:

https://www.virtualbox.org/wiki/Downloads

Configure docker-machine to use VirtualBox

Create a default machine (if you don't have one, see: docker-machine ls):

`docker-machine create --driver virtualbox default`

Then set-up the environment for the Docker client:

`eval "$(docker-machine env default)"`

Then double-check by listing containers:

`docker ps`


Then install the SupaBase containers locally

```bash
# Get the code
git clone --depth 1 https://github.com/supabase/supabase

# Go to the docker folder
cd supabase/docker

# Copy the fake env vars
cp .env.example .env

# Start
docker compose up
```