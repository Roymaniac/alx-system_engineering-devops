Use `su` become a Superuser for a short while

Use `whoami` get the username of the current user

Use `groups` to get all groups the current user is part of

Use `chown betty hello` to change the owner of the file `hello` to the user `betty`

Use `touch` to create an empty file called `hello`

Use `chmod u+x hello` to add execution permission to the owner of the file `hello`

Use `chmod ug+x,o+r hello` set execute permission for the `owner` &  `group owner`, and read permission for `other users`

Use `chmod a+x`to add execution permission on `owner`, `group owner` & `other user`

Use `chmod 007 hello` set permission to the file `hello` given each different permission

Use `chmod 753 hello` set the mode of all file `hello` to this `-rwxr-x-wx`

Use `chmod --reference=olleh hello`set the mode of file `hello` to the same as `olleh` mode

Use `chmod a+X *` add execute permission to all subdirectories of the current directory `owner`, `group owner` & all `other users` 

Use `mkdir -m 751 my_dir` create a directory called `my_dir` with the permission `751` in working directory

Use `chgrp school hello` to change the `group owner` to `school` for the file `hello`

Use `chown vincent:staff *` to change `owner` to `vincent` and `group owner` to `staff`

Use `chown -h vincent:staff _hello` to change the `owner` and `group owner` associated with the file `_hello`


Use`chown --from=guillaume betty hello` to change the `owner` if the file `hello` to `betty` if only it is owned by `guillaume`

Use `telnet towel.blinkenlights.nl` to play the Star wars episode IV in the terminal
