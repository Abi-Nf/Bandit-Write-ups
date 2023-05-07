# level19 -> level20

```sh
ssh bandit19@bandit.labs.overthewire.org -p 2220
# password : awhqfNnAbc1naukrpqDYcF95h7HoMTrC

ls
# bandit20-do 
./bandit20-do id
# uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)

./bandit20-do cat /etc/bandit_pass/bandit20
```

> The result : `VxCazJaVykI6W36BkBU0mJTCM8rR95XT`
