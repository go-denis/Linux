# Linux
Создаю скрипты BASH, работаю с LInux (Ubuntu)


## Задание:
Написать скрипт очистки директорий. На вход принимает путь к директории. Если директория существует, то удаляет в ней все файлы с расширениями .bak, .tmp, .backup. Если директории нет, то выводит ошибку.
* Создать скрипт ownersort.sh, который в заданной папке копирует файлы в директории, названные по имени владельца каждого файла. Учтите, что файл должен принадлежать соответствующему владельцу.

## Результат:
Код скриптов в текстовом виде (каждый скрипт в отдельном файле). Кодировка файлов UTF-8.

## Ход выполнения задания
- Создаем и открываем файл следующей командой (можно так же открыть в редакторе nano командой "nano delfiletodir"):
 cat > delfiletodir
- Пишем скрипт: 

#!/bin/bash

read -p "Введите путь к дирректории: " DELDIR

if [ -e $DELDIR ]
    then
        echo 'Указанная дирректория найдена'
        cd $DELDIR
        echo 'Произвожу удаление'
        rm -v *.bak *.tmp *.backup
        echo 'Удаление завершено успешно'
    else
        echo 'Указанная дирректория не найдена! Выполнение остановлено'
        exit 2
fi
