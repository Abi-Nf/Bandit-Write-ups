# level20 -> level21

```sh
ssh bandit20@bandit.labs.overthewire.org -p 2220
# password : VxCazJaVykI6W36BkBU0mJTCM8rR95XT

ls
# suconnect

# NB : we can create any port number we wants. example here : 3445
echo -n 'VxCazJaVykI6W36BkBU0mJTCM8rR95XT' | nc -l -p 3445 &
# [1] 326429

./suconnect  3445
```

> The result : `NvEJF7oVjkddltPSrdKEFOllh9V1IBcq`
