# level22 -> level23

```sh
ssh bandit22@bandit.labs.overthewire.org -p 2220
# password : WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

cat /etc/cron.d/cronjob_bandit23

cat /usr/bin/cronjob_bandit23.sh

echo I am user bandit23 | md5sum | cut -d ' ' -f 1
# got : 8ca319486bfbbc3663ea0fbe81326349

cat /tmp/8ca319486bfbbc3663ea0fbe81326349
```

> The result : `QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G`
