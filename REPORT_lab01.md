## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [ok ] 1. Ознакомиться со ссылками учебного материала
- [ok] 2. Выполнить инструкцию учебного материала
- [ok] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

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
`$ find . -type f -name "*.cpp" | wc -l  
$ find -not -name '*.cpp' -and -not -name '*.h' -and -not -name '*.hpp' | wc -l`  
6. Найдите полный путь до файла `any.hpp` внутри библиотеки *boost*.  
`$ find ~/boost_1_69_0 -name "any.hpp"`  
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.  
`$ grep -rnw ./ -e boost::asio`  
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).  
`$ ./bootstrap.sh —prefix=boost_output  
$ ./b2 install -j8`  
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.  
`$ mkdir ~/boost-libs  
$ mv *.* ~/boost-libs`  
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.  
`$ cd  
$ cd boost-libs  
$ du -a -h`  
11. Найдите *топ10* самых "тяжёлых".  
`$ du -a -h | sort -rh | head -n 10`  
