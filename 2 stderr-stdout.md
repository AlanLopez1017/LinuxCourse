## ;
We can concatenate two commands so that both are executed using ;. For example:

$whoami$; $ls$

  ## Concanting with an "and"
The second command is executed if the first command returns a successful status code.

$whoam$ && $ls$, since the $whoam$ command does not exist, it will not be successful, therefore, the second command will not be executed.

To see the status code you can do it using echo \$?, this shows the status code of the previously executed command. If it prints a 0, the status code is successful. If it shows a 1, 127, or another number (not 0), it tells us that it was not successful.

## Concanting with an "or"
$whoam$ || $ls$, here even if the first one is not correct, the second one will be executed anyway.

#Stderr
There are times when we are not interested when we are creating a bash script that the user sees errors in the console. This is what the stderr refers to and can be referenced with the number 2. Therefore, to redirect an error we do it as follows:

* $whoam$ 2>/dev/null

* /dev/null: It is a special existing resource so that anything we move here we disappear.


#Stdout
All that each command shows us when we execute it successfully is the stdout (output of the applied command). In case we want the stdout not to be seen, it is:

To redirect it by we can do it with the > symbol.

We want to send the output of $cat$ /etc/hosts to /dev/null. We do it like this: $cat$ /etc/hosts > /dev/null.
In case there is an error, right there we can make the stderr a stdout, so that it takes it as the output of the executed command itself and redirects it to /dev/null and it is done as follows:

* $cat$ /etc/hosts > /dev/null 2>$1

* Shorter form: $cat$ /etc/hosts &> /dev/null

## Put commands in the background

Any command that we want to run in the background we are going to add an '&' to the end.
Because this process will continue to be a child of the console, so when you close the console, the executed program is closed, to make said process independent and not depend on a main process because the same thing is done but at the end of everything it is placed the word 'disown'.