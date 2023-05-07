# Bandit exercices

click [here](https://overthewire.org/wargames/bandit/) to get to the site

## level0 -> level1

```sh
ssh bandit0@bandit.labs.overthewire.org -p 2220
password : bandit0
ls
# readme
cat readme
```

> The result : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

---

## level1-> level2

```sh
ssh bandit1@bandit.labs.overthewire.org -p 2220
# password : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

cat '/home/bandit1/-'
```

> The result : `rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`

---

## level2 -> level3

```sh
ssh bandit2@bandit.labs.overthewire.org -p 2220
# password : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

cd /home/bandit2
cat spaces\ in\ this\ filename
```

> The result : `aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG`

---

## level3 -> level4

```sh
ssh bandit3@bandit.labs.overthewire.org -p 2220
password : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

cd inhere
ls -al
# hidden file : .hidden
cat .hidden
```

> The result : `2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe`

---

## level4 -> level5

```sh
ssh bandit4@bandit.labs.overthewire.org -p 2220
password : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

cd inhere
ls -al
file ./-file*
# the file is -file07

cat ./-file07
```

> The result : `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`

---

## level5 -> level6

```sh
ssh bandit5@bandit.labs.overthewire.org -p 2220
password : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

cd inhere
find -type f -size 1033c ! -executable
## Sould be : ./maybehere07/.file2

cat ./maybehere07/.file2
```

> The result : `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`

---

## level6 -> level7

```sh
ssh bandit6@bandit.labs.overthewire.org -p 2220
password : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

cd /
cat /var/lib/dpkg/info/bandit7.password
```

> The result : `z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S`

---

## level7 -> level8

```sh
ssh bandit7@bandit.labs.overthewire.org -p 2220
password : z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

ls
# data.txt

grep 'millionth' ./data.txt
```

> The result : `TESKZC0XvTetK0S9xNwm25STk5iWrBvP`

---

## level8 -> level9

```sh
ssh bandit8@bandit.labs.overthewire.org -p 2220
TESKZC0XvTetK0S9xNwm25STk5iWrBvP

sort data.txt | uniq -u
```

---

> The result : `EN632PlfYiZbn3PhVK3XOGSlNInNE00t`

## level9 -> level10

```sh
ssh bandit9@bandit.labs.overthewire.org -p 2220
password : EN632PlfYiZbn3PhVK3XOGSlNInNE00t

cat data.txt | strings | grep ^=

# ========== password
# ========== is
# =TU%
# =^,T,?
# ========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

> I guess the password is : G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

---

## level10 -> level11

```sh
ssh bandit10@bandit.labs.overthewire.org -p 2220
password : G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

cat data.txt | base64 --decode
# The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

---

## level11 -> level12

```sh
ssh bandit11@bandit.labs.overthewire.org -p 2220
password : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
# The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

---

## level12 -> level13

```sh
ssh bandit12@bandit.labs.overthewire.org -p 2220
password : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

mkdir /tmp/myDir
xxd -r data.txt > /tmp/myDir/compressed.gz
gunzip compressed.gz
file compressed

# It shows : bzip2 compressed data, block size = 900k

mv compressed compressed.bz2
bzip2 -d compressed.bz2 
mv compressed compressed.gz
file compressed

# It shows : compressed: POSIX tar archive (GNU)

mv compressed compressed.tar
tar -xf compressed.tar

mv data5.bin data5.tar
tar -xf data5.tar

mv data6.bin data6.bz2
bzip2 -d data6.bz2

mv data6 data6.tar
tar -xf data6.tar

mv data8.bin data8.gz
gunzip data8.gz

cat data8
# The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

---

## level13 -> level14

```sh
ssh bandit13@bandit.labs.overthewire.org -p 2220
password : wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

eval $(ssh-agent)
ssh-add sshkey.private

ssh bandit14@bandit.labs.overthewire.org -p 2220
```

---

## level14 -> level15

```sh
cat /etc/bandit_pass/bandit14
# fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
nc localhost 30000
# Paste the current password
```

> result : jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

---

## level15 -> level16

```sh
ssh bandit15@bandit.labs.overthewire.org -p 2220
password : jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

openssl s_client -connect localhost:30001

# paste the current password
# jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

```

> result : JQttfApK4SeyHwDlI9SXGR50qclOAil1

---

## level16 -> level17

```sh
nmap localhost -p 31000-32000
openssl s_client localhost:31790

exit
```

I used Windows OS, so I did this on command line

- The [sshkey.private](./sshkey.private) file is here.

```cmd
eval $(ssh-agent)
ssh-add ./sshkey.private

ssh bandit17@bandit.labs.overthewire.org -p 2220
```

---

## level17 -> level18

```sh
diff password.old password.new
```

> result for the password.new (the password to use) : hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

---

## level18 -> level19

```sh
ssh bandit18@bandit.labs.overthewire.org -p 2220
## paste the password : hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

And I got this **error**

```sh
ByeBye !
Connection to bandit.labs.overthewire.org closed.
```

**Is game over ?**

I searched on net why I got `ByeBye` and wonder someone removed a file named `".bashrc"`

But the *password* for the next level is in a **`README`** file

So, let's force the ssh

```sh
ssh bandit18@bandit.labs.overthewire.org -p 2220 -t /bin/sh
## paste again the password : hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
ls
cat readme
```

> The result : awhqfNnAbc1naukrpqDYcF95h7HoMTrC

---

## level19 -> level20

```sh
ssh bandit19@bandit.labs.overthewire.org -p 2220
# password : awhqfNnAbc1naukrpqDYcF95h7HoMTrC

ls
# bandit20-do 
./bandit20-do id
# uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)

./bandit20-do cat /etc/bandit_pass/bandit20
```

> The result : VxCazJaVykI6W36BkBU0mJTCM8rR95XT

---

## level20 -> level21

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

> The result : NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

---

## level21 -> level22

```sh
ssh bandit21@bandit.labs.overthewire.org -p 2220
# password : NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

cd /etc/cron.d
cat cronjob_bandit22
ls
cat cronjob_bandit22.sh
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

> The result : WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

---

## level22 -> level23

```sh
ssh bandit22@bandit.labs.overthewire.org -p 2220
# password : WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

cat /etc/cron.d/cronjob_bandit23

cat /usr/bin/cronjob_bandit23.sh

echo I am user bandit23 | md5sum | cut -d ' ' -f 1
# got : 8ca319486bfbbc3663ea0fbe81326349

cat /tmp/8ca319486bfbbc3663ea0fbe81326349
```

> The result : QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

---

## level23 -> level24

```sh

```

> The result :

## level24 -> level25

```sh
```

> The result :

## level25 -> level26

```sh
```

> The result :

## level26 -> level27

```sh
```

> The result :

## level27 -> level28

```sh
```

> The result :

## level29 -> level30

```sh
```

> The result :

## level30 -> level31

```sh
```

> The result :

## level31 -> level32

```sh
```

> The result :

## level32 -> level33

```sh
```

> The result :

## level33 --> end

```sh
```

> The result :
