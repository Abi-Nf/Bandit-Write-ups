# level16 -> level17

```sh
nmap localhost -p 31000-32000
openssl s_client localhost:31790

exit
```

- The [sshkey.private](./sshkey.private) file is here.

```cmd
eval $(ssh-agent)
ssh-add ./sshkey.private

ssh bandit17@bandit.labs.overthewire.org -p 2220
```
