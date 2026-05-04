Завдання 1. Огляд активних процесів


1)
```bash
ps aux
```

USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
codespa+       1  0.0  0.0   1136   640 ?        Ss   10:40   0:00 /sbin/docker-init -- /bin/sh
root         256  0.0  1.1 2098744 96956 ?       Sl   10:40   0:00 dockerd --dns 168.63.129.16
codespa+    2088  1.4  4.1 44102876 338632 ?     Sl   10:42   0:29 node
...

2)
```bash
top
```

PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
2088 codespa+  20   0   42.1g 338632  56576 S   0.0   4.2   0:30.32 node
2054 codespa+  20   0   11.3g 114416  52224 S   0.0   1.4   0:05.95 node
...

```bash
ps aux --sort=-%mem | head -10
```

USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
codespa+    2088  1.4  4.1 44102876 338632 ?     Sl   10:42   0:30 node
codespa+    2054  0.2  1.4 11844248 115312 ?     Sl   10:42   0:05 node
...

3)
```bash
echo $SHELL
echo $$
ps -p $$
```

/bin/bash
19406
PID TTY          TIME CMD
19406 pts/1    00:00:00 bash


Завдання 2. Робота у фоні та керування процесами


1)
```bash
sleep 1000 &
```

[1] 20709

2)
```bash
jobs
```

[1]+  Running                 sleep 1000 &

3)
```bash
fg %1
```
Ctrl+Z
sleep 1000
^Z
[1]+  Stopped                 sleep 1000

4)
```bash
jobs -l
```

[1]+ 20709 Stopped                 sleep 1000

5)
```bash
kill -9 20709
jobs
```

[1]+  Killed                  sleep 1000

6)
```bash
nohup sleep 500 > nohup_output.txt 2>&1 &
ps aux | grep sleep
ls -la nohup_output.txt
```

[1] 22012
codespa+   22012  0.0  0.0   6116  1792 pts/1    S    11:20   0:00 sleep 500
-rw-rw-rw- 1 codespace codespace 22 May  4 11:20 nohup_output.txt


Завдання 3. Пріоритети та обмеження


1)
```bash
nice -n 10 sleep 300 &
ps -o pid,ni,cmd -p $!
```

[2] 22512
PID  NI CMD
22512  10 sleep 300

2)
```bash
sudo renice 15 -p $!
ps -o pid,ni,cmd -p $!
```

22512 (process ID) old priority 10, new priority 15
PID  NI CMD
22512  15 sleep 300

3)
```bash
ulimit -a
```

real-time non-blocking time  (microseconds, -R) unlimited
core file size              (blocks, -c) unlimited
data seg size               (kbytes, -d) unlimited
open files                          (-n) 524288
stack size                  (kbytes, -s) 8192
...


4)

```bash
df -h
```

Filesystem      Size  Used Avail Use% Mounted on
overlay          32G  9.6G   21G  33% /
/dev/root        29G   19G   11G  64% /vscode
/dev/sda1        44G  2.9G   39G   7% /tmp

2)
```bash
free -h
```

total        used        free      shared  buff/cache   available
Mem:           7.8Gi       1.7Gi       247Mi        63Mi       6.2Gi       6.1Gi
Swap:             0B          0B          0B
