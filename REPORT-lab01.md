## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [ok] 1. Ознакомиться со ссылками учебного материала
- [ok] 2. Выполнить инструкцию учебного материала
- [ok] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
$ export GITHUB_USERNAME=<имя_пользователя>    #присваиваем <имя_пользователя> в переменную GITHUB_USERNAME
$ export GIST_TOKEN=<сохраненный_токен>       #присваиваем <сохраненный_токен> в переменную GIST_TOKEN
$ alias edit=<nano|vi|vim|subl>              #выбираем какой редактор хотим открыть
```

```sh
$ mkdir -p ${GITHUB_USERNAME}/workspace    #создаем директорию workspace
$ cd ${GITHUB_USERNAME}/workspace         #спускаемся в созданную workspace
$ pwd                                    #выводим в терминал путь к текущей папке
$ cd ..                                 #поднимаемся обратно
$ pwd                                  #выводим в терминал путь к текущей папке
```

```sh
$ mkdir -p workspace/tasks/        #создаем в workspace директорию tasks
$ mkdir -p workspace/projects/    #создаем в workspace директорию projects
$ mkdir -p workspace/reports/    #создаем в workspace директорию reports
$ cd workspace                  #спускаемся в workspace
```

```sh
# Debian
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz  #скачиваем файл
$ tar -xf node-v6.11.5-linux-x64.tar.xz                              #извлекаем файл из архива
$ rm -rf node-v6.11.5-linux-x64.tar.xz                              #удаляем файл (в нашем случае-архив)
$ mv node-v6.11.5-linux-x64 node                                   #переименовываем на "node"
```

```sh
$ ls node/bin                              #выводим содержимое папки
$ echo ${PATH}                            #посмотреть содержимое переменной PATH
$ export PATH=${PATH}:`pwd`/node/bin     #добавляем новый путь к переменной PATH
$ echo ${PATH}                          #убедимся, что в переменной PATH содержится имя, добавленной, папки
$ mkdir scripts                        #создаем scripts
$ cat > scripts/activate<<EOF         #создаем файл и пишем данные от EOF до EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate          #выполням команду из файла activate
```

```sh
$ gem install gist     #установка последней версии gist
```

```sh
$ (umask 0077 && echo ${GIST_TOKEN} > ~/.gist)   #берем права для директории
```

## Report

```sh
$ export LAB_NUMBER=01                                                          #присваиваем 01 в переменную LAB_NUMBER
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER} #клонируем из ссылки в директорию (в наше случае-tasks/lab01)
$ mkdir reports/lab${LAB_NUMBER}                                              #создаем директорию (в наше случае- lab01)                                      
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md     #спускаемся в директорию (в наше случае- lab01)
$ cd reports/lab${LAB_NUMBER}                                               #копируем из одной директории в другую
$ edit REPORT.md                                                           #редактируем REPORT.md
$ gist REPORT.md                                                          #сохраняем REPORT.md
```

## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)

## Homework

1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.  
`$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`  
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`  
`$ tar -xvzf boost_1_69_0.tar.gz -C ~/boost_1_69_0/`  
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.  
`$ cd boost_1_69_0  
$ ls | wc -l`  
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.  
`find ./ -type f | wc -l`  
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).  
`
$ find . -type f -name "*.cpp" | wc -l`  
`$ find -not -name '*.cpp' -and -not -name '*.h' -and -not -name '*.hpp' | wc -l`   
6. Найдите полный путь до файла `any.hpp` внутри библиотеки *boost*.  
`$ find ~/boost_1_69_0 -name "any.hpp"`  
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.  
`$ grep -rnw ./ -e boost::asio`  
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).  
`$ ./bootstrap.sh —prefix=boost_output`  
`$ ./b2 install -j8`  
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.  
`$ mkdir ~/boost-libs`  
`$ mv *.* ~/boost-libs`  
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.  
`$ cd`  
`$ cd boost-libs`  
`$ du -a -h`  
11. Найдите *топ10* самых "тяжёлых".  
`$ du -a -h | sort -rh | head -n 10`  

```
Copyright (c) 2015-2021 The ISC Authors
```
