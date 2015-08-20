# docker-environment
A tool to manage your docker environment, much simpler than docker-machine

Create ~/.dockenv as a yaml file like this

     name1:
        ssh:  connect1
     
     name2;
        ssh:  connect2
	port: 1234

you can then run 'dockerenv name1' and be placed in a shell your
DOCKER_HOST environment variable tunneled to the remote host, port
4243.  'dockerenv name2' will put you in a shell with DOCKER_HOST
tunneled through ssh connect2 to port 1234.


