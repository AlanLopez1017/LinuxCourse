* We are a user at the system level -> We can check which user we are with $whoami$

* $id:$ you can see which groups they belong to. Each user normally is assigned a group with the same name. When pentesting is carried out, seeing at each moment which group we are in is interesting because there are groups that may present a potential risk in the face of an escalation of privileges.

* Being in the sudo group allows privilege to be escalated from the current user to the root user.
$sudo su$: Requests a password from the previously assigned user. Escalate to root user. The root user is the one with the greatest privileges at the system level.

* $exit$: Exit the current session as root and return to the non-privileged user.

* We can use the word $sudo$ followed by the command we want to use without needing to be the root user.

* We can see all the groups within $id$ within a system path found in /etc/group

* $cat$ helps us list the content of the following parameter: $cat$ /etc/group shows us the content of /etc/group, we see all the existing groups and the group identifier at the end.

* When we execute a command, for example, $whoami$, it is the execution of the command $whoami$ (binary) using a relative path, that is, it is not necessary to specify its absolute path. Each binary should have an absolute path and can be obtained using $which$ [command]. The absolute path of $whoami$ is /usr/bin/whoami, therefore, the execution of said command can also be done by writing said absolute path.

* There is an environment variable that helps us manage this, so that it is not necessary to write the entire path for the binaries, this variable is PATH: It contains several paths separated by colons, which is an order of priority existing throughout the which when we execute the [command] it begins to search for it in each of the routes located in PATH.

* $grep$ helps apply filters supported by: |. So, if we want to filter by the id of a specific group we can do $cat$ /etc/group | grep "group_name".

* $command$ -v [command] is used in case which cannot be executed in some command.

* $pwd$: current path

* $ls$: Lists the contents of a file. With the -l parameter you can list in detail the current resources of the current working directory. The path can be specified: ls [path].

* $cd$(change directory): We migrate directories. Example: Go to the downloads directory -> $cd$ Download. To return to the previous directory, use a ".." -> $cd$ ..
To specify a specific path -> $cd$ /home/user/
To go to the root of the system it is done using $cd$ /

* $HOME: Here it tells you the user's personal directory.

* /etc/passwd: Here the users are shown at the system level, with their user identifiers, group identifiers, personal directory and finally the type of shell used.

* $SHELL: The type of shell used.

* /etc/shell: Shell types.

