## Processes And Signal

Write a Bash script that displays its own PID

```bash
echo $$
```

Write a Bash script that displays its own PID

```bash
ps -faux
```

Using your previous exercise command, write a Bash script that displays lines containing the bash word, thus allowing you to easily get the PID of your Bash process.

```bash
ps -faux | grep "bash"
```

Write a Bash script that displays the PID, along with the process name, of processes whose name contain the word bash

```bash
pgrep -1 "bash"
```

Write a Bash script that displays To infinity and beyond indefinitely.

```bash
while true
do
    echo "To infinity and beyond"
    sleep 2
done
```

Write a Bash script that stops 4-to_infinity_and_beyond process.

```bash
kill "$(pgrep -f 4-to_infinity_and_beyond)"
```

Write a Bash script that stops 4-to_infinity_and_beyond process, without using kill

```bash
pkill -f 4-to_infinity_and_beyond
```

Write a Bash script that displays:

* To infinity and beyond indefinitely
* With a sleep 2 in between each iteration
`I am invincible!!!` when receiving a SIGTERM signal

```bash
while true
do
    echo "To infinity and beyond"
    sleep 2
    trap 'echo "I am invincible!!!"' SIGTERM
done
```

Write a Bash script that kills the process 7-highlander.

```bash
pkill -SIGKILL -f "7-highlander"
```

Write a Bash script that:

* Creates the file /var/run/myscript.pid containing its PID
* Displays To infinity and beyond indefinitely
* Displays I hate the kill command when receiving a SIGTERM signal
* Displays Y U no love me?! when receiving a SIGINT signal
* Deletes the file /var/run/myscript.pid and terminates itself when receiving a SIGQUIT or SIGTERM signal

```bash
sudo touch /var/run/myscript.pid
sudo bash -c 'echo $$ > /var/run/myscript.pid'
while true
do
    echo "To infinity and beyond"
    sleep 2
    trap 'echo "I hate the kill command"; sudo rm /var/run/myscript.pid; exit' SIGTERM
    trap 'echo "Y U no love me?!"' SIGINT
    trap 'sudo rm /var/run/myscript.pid; exit' SIGQUIT
done
```

Write Bash (init) script 101-manage_my_process that manages manage_my_process. (both files need to be pushed to git)

Requirements:

> When passing the argument start:
* Starts manage_my_process
* Creates a file containing its PID in /var/run/my_process.pid
* Displays manage_my_process started
> When passing the argument stop:
* Stops manage_my_process
* Deletes the file /var/run/my_process.pid
* Displays manage_my_process stopped
> When passing the argument restart
* Stops manage_my_process
* Deletes the file /var/run/my_process.pid
* Starts manage_my_process
* Creates a file containing its PID in /var/run/* my_process.pid
> Displays manage_my_process restarted
Displays Usage: manage_my_process {start|stop|restart}

```bash
if [ "${1}" == "start" ]
then
    ./manage_my_process &
    touch /var/run/my_process.pid
    echo "$!" > /var/run/my_process.pid
    echo "manage_my_process started"
elif [ "${1}" == "stop" ]
then
    echo "manage_my_process stopped"
    kill "$(cat /var/run/my_process.pid)"
    rm /var/run/my_process.pid
elif [ "${1}" == "restart" ]
then
    kill "$(cat /var/run/my_process.pid)"
    rm /var/run/my_process.pid
    ./manage_my_process &
    touch /var/run/my_process.pid
    echo "$!" > /var/run/my_process.pid
    echo "manage_my_process restarted"
else
    echo "Usage: manage_my_process {start|stop|restart}"
fi
```

Write a C program that creates 5 zombie processes.

Requirements:

* For every zombie process created, it displays Zombie process created, PID: ZOMBIE_PID
* Your code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
* When your code is done creating the parent process and the zombies, use the function bellow

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

/**
 * infinite_while - creates an infinite loop to make the program hang
 * Return: always 0
 */
int infinite_while(void)
{
	while (1)
	{
		sleep(1);
	}
	return (0);
}

/**
 * main - creates 5 zombie processes
 * Return: always 0
 */
int main(void)
{
	int i;
	pid_t zombie;

	for (i = 0; i < 5; i++)
	{
		zombie = fork();
		if (!zombie)
			return (0);
		printf("Zombie process created, PID: %d\n", zombie);
	}

	infinite_while();
	return (0);
}

```