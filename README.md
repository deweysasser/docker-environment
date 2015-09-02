# docker-environment
A tool to manage your docker environment, much simpler than docker-machine

Create ~/.dockerenv as a yaml file like this

     name1:
        ssh:  user@host1
     
     name2:
        ssh:  user2@connect2
	port: 1234

     name3:
        address: my-docker-host.example.com

you can then run 'dockerenv <name>' and you will be placed in a shell
with your DOCKER_HOST environment variable set to the appropriate
value.  

If the connection method specifies SSH, an SSH tunnel will be created
for the lifetime of your shell and your connection will be tunneled
through that session.


