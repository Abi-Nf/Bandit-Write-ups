# level12 -> level13

```sh
ssh bandit12@bandit.labs.overthewire.org -p 2220
# password : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

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
```

> The result : `wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw`
