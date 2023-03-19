## First Steps 

#### python

```bash
python -c 'import pty;pty.spawn("/bin/bash")'
```

#### python2

```bash
python2 -c 'import pty;pty.spawn("/bin/bash")'
```

#### python3

```bash
python3 -c 'import pty;pty.spawn("/bin/bash")'
```

#### ruby

```bash
ruby -e "exec '/bin/bash'"
```

#### perl

```bash
perl -e "exec '/bin/bash'"
```

## Host Shell

#### Remove echo

```bash
CONTROL+Z
stty raw -echo; fg
```

## Last Step

#### Export the term

```bash
export TERM=xterm
```
