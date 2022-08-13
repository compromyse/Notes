# King Of The Hill

## Find SUID files

```bash
find / -type f \( -perm -4000 -o -perm -2000 \) -print 2>/dev/null
```

## Nyancat troll

```bash
export PTSNUM=; ./nyancat > /dev/pts/$PTSNUM & disown
```

## Urandom troll

```bash
export PTSNUM=; cat /dev/urandom > /dev/pts/$PTSNUM & disown 
```

## King.txt

```bash
while [ 1 ]; do chattr -i /root/king.txt; echo "compromyse" > /root/king.txt; chattr +i /root/king.txt; done
```

