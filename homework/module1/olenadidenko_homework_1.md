Завдання 1. Базові команди

1) pwd
   ls
/Users/elena
1            Pictures            ...
Applications Public              ...
Desktop      ...                 ...
Documents    ...                 ...
Downloads    html-media          smth.java
IdeaProjects pds.html            src
Library      jest.config.js      test-utils
Movies       node_modules
Music        packa

2) cd Downloads
   pwd
   ls
/Users/elena/Downloads
ls: .: Operation not permitted

3) > test.txt
4) cat test.txt
   (пусто)
6) cd /Users/$USER
   pwd
/Users/elena

7) cd ..
   pwd
   cd ~
   pwd
/Users
/Users/elena


Завдання 2. Робота з документацією

Команди:
  man ls
  help cd
  man cat
  man man
  cp --help
  mv --help

cd: cd [-L|-P] [dir]
    Change the current directory to DIR.  The variable $HOME is the
    default DIR.  The variable CDPATH defines the search path for
    the directory containing DIR...

cp: illegal option -- -
usage: cp [-R [-H | -L | -P]] [-fi | -n] [-aclpSsvXx] source_file target_file
       cp [-R [-H | -L | -P]] [-fi | -n] [-aclpSsvXx] source_file ... target_directory

mv: illegal option -- -
usage: mv [-f | -i | -n] [-hv] source target
       mv [-f | -i | -n] [-v] source ... directory

1) ls -a
2) can -n
3) man відкриває детальну інструкцію для зазначеної команди
   --help виводить короткий список опцій


Завдання 3. Міні-сценарій

Команди: 
  cd ~
  mkdir -p zav3
  cd zav3
  > file1.txt
  ls
  cd ..
  pwd
  cd zav3
  man ls

file1.txt
/Users/elena
  q
