---
layout: post
comments: true
title:  Running jobs over SSH
author: joao
---

My laptop isn't really a number crunching beast,
but over at work I have a relatively powerful PC 
which is turned on almost 24/7.
How to run more demanding jobs in the PC at work?


## the setup

So here's the setup.
I'm at home with my `laptop`, running linux and with SSH installed.
In order to SSH into my work computer (`work`)
I need to create an SSH tunnel that goes through a front-end public `server`.
Beforehand, at `work`, I got my IP address with the command.

```
(work)$ ifconfig
eth0      ....
          inet addr:WORK_IP_ADDRESS  
....

```


Then at home (or anywhere with internet) the command

```
(laptop)$ ssh -N -f -L 2200:WORK_IP_ADDRESS:22 user1@server
```

creates the SSH tunnel. 
For `user1` you should use your username in the `server`,
the one that allows you to do

```
(laptop)$ ssh user1@server
```

These two last commands might ask you for a password.  
Now that the tunnel is open, let's SSH into the `work` computer

```
(laptop)$ ssh -XC -p 2200 user2@localhost
```

This command used port 2200 to go into localhost, 
which itself is pointing to `work`.  
Note that `user2` might be different from `user1`.
The former is your username at `work`.


In the previous command, the `-XC` options 
turn on both the display and compression, respectively.
This basically allows for plots to show up
and speeds things up (quite) a bit.
Feel free to experiment without including those options.



## running jobs

Ok, now we're at the `work` computer and we want to run a job
that will take a bit of time to complete.
If we just do

```
(work)$ ./job
```

the terminal is stuck showing the output of the job,
and nasty things might happen if you turn off the laptop
(I'm not sure what will happen, but it might be nasty).  
Even if you run

```
(work)$ ./job &
```

the output of the job will still show up in the terminal.  

The solution is to use `nohup`.  
The following command will run the job without blocking the terminal

```
(work)$ nohup ./job > job.log 2>&1 &
```

and the output is piped to a file called `job.log`.
Those last characters (`2>&1`) put any errors (stderr) in `job.log` as well,
and `&` runs the command in the background.

Ok, so now the job is running and your terminal isn't blocked.
But if you type `exit` to close the SSH connection 
(because you want to turn off the `laptop` and go to sleep)
the terminal will tell you that you have running jobs.
If you insist, by typing `exit` again, the job will be stopped.
There are two ways to solve this.

One way is to run

```
(work)$ jobs
[1]  + running    nohup ./job > job.log 2>&1
(work)$ disown %1
```

the other, which works if you use the zsh shell, 
is to just append a `!` to that initial `nohup` command, like this:

```
(work)$ nohup ./job > job.log 2>&1 &!
```

which automatically disowns the job.  
Either way, you will now be able to close the SSH connection 
without stopping the job.


## wrap up

```
(laptop)$ ssh -N -f -L 2200:WORK_IP_ADDRESS:22 user1@server
(laptop)$ ssh -XC -p 2200 user2@localhost
(work)$ nohup ./job > job.log 2>&1 &!
(work)$ exit
(go to sleep)
```

Let me know in the comments if this is helpful, wrong or super-duper cool.





