# level18 -> level19

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

> The result : `awhqfNnAbc1naukrpqDYcF95h7HoMTrC`
