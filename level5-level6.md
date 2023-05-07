# level5 -> level6

```sh
ssh bandit5@bandit.labs.overthewire.org -p 2220
# password : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

cd inhere
find -type f -size 1033c ! -executable
## Sould be : ./maybehere07/.file2

cat ./maybehere07/.file2
```

> The result : `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`
