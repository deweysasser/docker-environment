ARCHIVED
========

This project is no longer maintained.  If someone would like to adopt it I'll be happy to transfer it.

---

# docker-environment 

A tool to manage your docker environment, much simpler than
docker-machine.

I find myself running ‘docker’ commands against a number of hosts.  I
wrote this tool to manage host connections for me (I would likely have
used docker-machine had it worked on Cygwin out of the box).

Create ~/.dockerenv as a yaml file like this

     name1:
        ssh:  user@host1
     
     name2:
        ssh:  user2@connect2
	port: 1234

     name3:
        address: my-docker-host.example.com

you can then run 'dockerenv NAME' and you will be placed in a shell
with your DOCKER_HOST environment variable set to the appropriate
value.  (In this example, NAME would be one of 'name1', 'name2' or
'name3'.)

If the connection method specifies SSH, an SSH tunnel will be created
for the lifetime of your shell and your connection will be tunneled
through that session.

## Connection Types

This tool supports:

* 'address' -- a direct TCP connection to the given address
* 'ssh' -- tunnel the connection through SSH to the given SSH connection string.

Both connection methods can have a 'port' associated.  If no port is
defined, it defaults to the IANA issued docker standard of 2375.


TODO
----

* create a bash completion function to complete names create a
* convenience method to ssh directly to 'current' docker host make
* this act more like virtualenv and avoid so much subshell stuff
  (which also impacts CWD)
