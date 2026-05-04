Задвання 1. Ієрархія каталогів Linux

1)
```bash
cd /
pwd
ls -la
```

/

total 100

drwxr-xr-x    1 root      root   4096 May  4 10:40 .

drwxr-xr-x    1 root      root   4096 May  4 10:40 ..

drwxr-xr-x    3 root      root   4096 May  4 10:40 .codespaces

-rwxr-xr-x    1 root      root      0 May  4 10:40 .dockerenv

lrwxrwxrwx    1 root      root      7 Apr 22  2024 bin -> usr/bin

drwxr-xr-x    2 root      root   4096 Jul 10  2025 bin.usr-is-merged

drwxr-xr-x    2 root      root   4096 Apr 22  2024 boot

drwxr-xr-x   13 root      root   3940 May  4 10:40 dev

drwxr-xr-x    1 root      root   4096 May  4 10:42 etc
...

2)
```bash
cd /etc
pwd
ls -la
```
/etc
total 772
drwxr-xr-x 1 root root    4096 May  4 10:42 .
drwxr-xr-x 1 root root    4096 May  4 10:40 ..
-rw------- 1 root root       0 Feb 10 14:05 .pwd.lock
drwxr-xr-x 2 root root    4096 Jun  3  2024 ODBCDataSources
drwxr-xr-x 2 root root    4096 Mar 11 11:59 PackageKit
drwxr-xr-x 1 root root    4096 Mar 11 11:59 X11
-rw-r--r-- 1 root root    3444 Jul  5  2023 adduser.conf
drwxr-xr-x 1 root root    4096 Mar 11 12:18 alternatives
drwxr-xr-x 3 root root    4096 Mar 11 11:59 apache2
drwxr-xr-x 3 root root    4096 Mar 11 12:00 apparmor.d
drwxr-xr-x 1 root root    4096 Apr  6 00:22 apt
-rw-r--r-- 1 root root    5250 Mar 11 12:19 bash.bashrc
-rw-r--r-- 1 root root      45 Jan 24  2020 bash_completion
drwxr-xr-x 1 root root    4096 Apr  6 00:22 bash_completion.d
...

3)
```bash

cd /home
pwd
ls -la
```

/home
total 24
drwxr-xr-x 1 root      root      4096 May  4 10:40 .
drwxr-xr-x 1 root      root      4096 May  4 10:40 ..
drwxr-x--- 1 codespace codespace 4096 May  4 10:42 codespace
drwxr-xr-x 3 root      root      4096 May  4 10:40 vscode


Завдання 2. Файли, каталоги та посилання

1)
```bash
cd ~
pwd
mkdir lab2
ls -la
```

/home/codespace
...
drwxr-xr-x 2 codespace codespace 4096 May  4 10:44 lab2

2)
```bash
cd lab2
pwd
touch file.txt
ls -la
```

/home/codespace/lab2
total 12
drwxr-xr-x 2 codespace codespace 4096 May  4 10:44 .
drwxr-x--- 1 codespace codespace 4096 May  4 10:44 ..
-rw-r--r-- 1 codespace codespace    0 May  4 10:44 file.txt

3)
```bash
echo "Hello Linux" > file.txt
cat file.txt
```

Hello Linux

4)
```bash
cp file.txt file_copy.txt
ls -la
```

total 20
drwxr-xr-x 2 codespace codespace 4096 May  4 10:45 .
drwxr-x--- 1 codespace codespace 4096 May  4 10:44 ..
-rw-r--r-- 1 codespace codespace   12 May  4 10:44 file.txt
-rw-r--r-- 1 codespace codespace   12 May  4 10:45 file_copy.txt

5)
```bash
mv file_copy.txt renamed_copy.txt
ls -la
```

total 20
drwxr-xr-x 2 codespace codespace 4096 May  4 10:45 .
drwxr-x--- 1 codespace codespace 4096 May  4 10:44 ..
-rw-r--r-- 1 codespace codespace   12 May  4 10:44 file.txt
-rw-r--r-- 1 codespace codespace   12 May  4 10:45 renamed_copy.txt

6)
```bash
ln file.txt hardlink_file.txt
ls -la
```

total 24
drwxr-xr-x 2 codespace codespace 4096 May  4 10:45 .
drwxr-x--- 1 codespace codespace 4096 May  4 10:44 ..
-rw-r--r-- 2 codespace codespace   12 May  4 10:44 file.txt
-rw-r--r-- 2 codespace codespace   12 May  4 10:44 hardlink_file.txt
-rw-r--r-- 1 codespace codespace   12 May  4 10:45 renamed_copy.txt

7)
```bash
ln -s file.txt symlink_file.txt
ls -la
```

lrwxrwxrwx 1 codespace codespace    8 May  4 10:45 symlink_file.txt -> file.txt

8)
```bash
cat hardlink_file.txt
cat symlink_file.txt
```

Hello Linux
Hello Linux

9)
```bash
find /home -name file.txt
```

/home/codespace/lab2/file.txt


Завдання 3. Права доступу

1)
```bash
cd ~/lab2
pwd
ls -l file.txt
```

/home/codespace/lab2
-rw-r--r-- 2 codespace codespace 12 May  4 10:44 file.txt

2)
```bash
chmod 444 file.txt
ls -l file.txt
```

-r--r--r-- 2 codespace codespace 12 May  4 10:44 file.txt

3)
```bash
chmod u+w file.txt
ls -l file.txt
```

-rw-r--r-- 2 codespace codespace 12 May  4 10:44 file.txt

4)
```bash
umask
```

0022

5)
```bash
umask 022
umask
```

0022


Завдання 4. Користувачі

1)
```bash
sudo useradd -m trainee
```

2)
```bash
sudo usermod -aG sudo trainee
```

3)
```bash
cat /etc/passwd | grep trainee
```

trainee:x:1001:1002::/home/trainee:/bin/sh
