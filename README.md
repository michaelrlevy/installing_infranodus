### Infranodus is a text-to-network-graph system. Here is how to install it

On my WSL 2 Ubuntu 18.04, apache2 is already installed

Instructions on installing Infranodus server are here https://github.com/noduslabs/infranodus/wiki/Server-Setup

Note it doesn't work with systemctl, but rather
```
sudo service apache2 start
```
Install Node
```
sudo apt install nodejs
```
make a directory and cd into it and then
```
git clone https://github.com/noduslabs/infranodus.git
```
Create and edit config.json with this:
```JSON
  {
      "neo4j":  {
          "host": "localhost:7474",
          "username": "",
          "password": ""
      },
      "secrets": {
          "invitation": "invite_code"
      }
  }
```
On my WSL 2 Ubuntu 18.04, I already have Java OpenJDK instaled, version 10.0.2

Note there is a slight bug in the Infranodus install docs. Where they have 
cd ~ wget http://dist.neo4j.org/neo4j-community-2.0.1-unixtar; and the final cd should be on 4 lines.
And then to start the server, it's
```
bin/neo4j start
```

I had to separately install npm
```
sudo apt instlal npm
```
after which
```
npm -v
```
results in
```
3.5.2
```
Install pm2:
```
npm install pm2@latest -g
```
I saw some warnings but they are only warnings, not errors
```
npm WARN optional Skipping failed optional dependency /pm2/chokidar/fsevents:
npm WARN notsup Not compatible with your operating system or architecture: fsevents@1.2.9
```

