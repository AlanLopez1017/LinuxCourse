We do the following:

# Create file descriptor

* $exec$ 3<> file

This creates a file called 'file'. We are using a file descriptor identified with the number 3. The < I told us has read and > write capabilities. So the command we run has both capabilities.

If we now perform a command like $whoami$ and we want the output to be written to the file we created, we do it as follows.

* $whoami$ >&3: stores the output of the command in the 'file'.

Anything we continue to add to the file will do so as an 'append'.

# Close file descriptor

* $exec$ 3>&-

This does not mean that the file has lost its content, but rather that if you want to put an output to the file it will say the following error: bad file descriptor, because that file descriptor will no longer exist at the time of closing it.

## Copies between file descriptors

We create a descriptor 5 for the data file:

* $exec$ 5<> data

* $whoami$ >&5

Now we create a descriptor 8 and what is in file descriptor 5 will create a copy for said file descriptor 8:

* $exec$ 8>&5

For example, now if we perform $pwd$ >&5, the command will be entered in both descriptors 5 and 8.

When we create the copy, we can close the first descriptor on the fly so that we can put content inside the second descriptor directly, but no longer explicitly inside the second one with >&.