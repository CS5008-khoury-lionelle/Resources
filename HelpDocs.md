# Help Docs

This is a list of issues that are common for students, and will eventually be updated as issues change. It may not be the most up to date, so if you have any questions, please ask your instructor.


## Error: -bash: fork: retry: No child processes

This error is caused by a lack of memory. You can fix this by closing any programs. On the Khoury Servers when using VSCode Remote what open happens is students don't exit the program properly leaving instances on the server.  

This can be fixed by: 

```bash
pkill -u your_username
```

If that doesn't work, you can try:

```bash
pkill -u your_username -9
```
You can view all the processes running on the server by running:

```bash
ps -u your_username
```
or

```bash
ps aux | grep your_username
```

## Error: Disk quota exceeded

This can especially happy if you have tar: vscode-server-x64/..../  Cannot mkdir: Disk quota exceeded.

This is caused by a lack of space on the server. You can fix this by deleting files. Really, the real issue is that
vscode keeps a lot of backup files. You can fix this by deleting the .vscode-server folder in your home directory. 

Log in via the terminal and run:

```bash
rm -rf .vscode-server
```

Then reconnecting with your remote. If your VSCode has a process running, you look at [bash process](#error-bash-fork-retry-no-child-processes) section for the kill commands.

### Looking at disk quota
Before you start removing files, it is also good to see which file directories are the biggest! You can do that by running:

```bash
du --exclude=.snapshot -h --max-depth=1 ~ | sort -hr
```


## Error: Got error from ssh: spawn

This can happen sometimes with updates to VSCode causing your remote-ssh extension to fail. Students found this [Stack Overflow](https://stackoverflow.com/questions/67976875/vs-code-remote-ssh-the-vscode-server-failed-to-start-ssh) helped them with the error.

