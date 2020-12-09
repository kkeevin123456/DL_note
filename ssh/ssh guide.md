# On Windows

Requirement:

Install OpenSSH

Step1:

> ```ssh-keygen -t rsa```

Step2:

> Path: ```.\.ssh\bujo0```

Step3:

> ```ssh -i ".\.ssh\bujo0" datalab@140.114.88.21```

# Linux

Use following script

On remote jump server

```
ssh-keygen -t rsa -f ~/.ssh/bujo-plus
ssh-copy-id -i ~/.ssh/bujo-plus ccchen@netdb-bujoplus0
ssh -i "~/.ssh/bujo-plus" ccchen@netdb-bujoplus0
```

Then, on local host(windows). Copy the private key to the local host

```
scp datalab@140.114.88.21:/home/datalab/.ssh/bujo-plus .\.ssh\
```

Connect to remote target server:

With local hostname(windows)

```
ssh -o ProxyCommand="C:\Windows\System32\OpenSSH\ssh.exe -q -W %h:%p 140.114.88.21"  ccchen@192.168.1.151 -i ".ssh/bujo-plus"
```

With IP address(windows)

```
 ssh -o ProxyCommand="C:\Windows\System32\OpenSSH\ssh.exe -q -W %h:%p 140.114.88.21"  ccchen@netdb-bujoplus0 -i ".ssh/bujo-plus"
 ```

# Something Important

Since Window seperate the directory with ```\``` but Linux ```/```, all the paths on Window should add ```" "``` across the path.

# Reference

1. [scp-ssh copy](https://blog.gtwang.org/linux/linux-scp-command-tutorial-examples/)
2. [Login SSH without password on Linux with ssh-copy-id](https://www.ibm.com/support/pages/configuring-ssh-login-without-password)
3. [ssh-copy-id on Windows](https://serverfault.com/questions/224810/is-there-an-equivalent-to-ssh-copy-id-for-windows)
4. [Specify ssh-keygen target file](https://superuser.com/questions/1004254/how-can-i-change-the-directory-that-ssh-keygen-outputs-to/1004263)
5. [SSH & Github](https://pjchender.github.io/2018/05/31/is-%E9%97%9C%E6%96%BC-ssh/)