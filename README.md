# phppgadmin
A phppgadmin instance.
The main goal in front of the others phppgadmin containers is to offer a simple 'ready to use' one.
You just set the ENV variables and access from the url of the container.
No more /phppgadmin, this is a phppgadmin dedicated container ... no need to repeat.

## Usage

First make the image :  
`docker build -t zhajor/docker-phppgadmin .`  
Then a container :  
`docker run -d -p 12345:80 -e "DB_HOST=192.168.99.100,192.168.99.101" --name=postg zhajor/docker-phppgadmin`

Replace DB_HOST by your ip or the virtualhost made by --link or networks, for example:
`docker run -d --name=postgres-db postgres`  
`docker run -d -p 12345:80 --link postgres-db:postgres-db -e "DB_HOST=postgres-db"  --name=postg zhajor/docker-phppgadmin`

You can now access the phppgadmin interface from http://127.0.0.1:12345/
