# Operation_Systems_LB1

Для повышение безопасности информационной системы, часто используют изолированность подсистем друг от друга.

Изоляция может быть аппаратной и программной.

Программная изоляция реализуется с помощью "виртуальных машин".

Виртуальная машина -  подробнее в wikepedia

Наиболее распространенные виртуальные машины:

VirtualBox (Oracle) (https://www.virtualbox.org/,  http://ru.wikipedia.org/wiki/VirtualBox) 
VMware Workstation (http://www.vmware.com/ ,http://ru.wikipedia.org/wiki/VMware_Workstation)
Virtual PC (microsoft) (http://ru.wikipedia.org/wiki/Virtual_PC)
Не забывайте создавать резервные копии своей виртуальной машины!

Образ виртуальной машины возьмите здесь - http://kfti.knc.ru/edu/
образ Fedora login - root, password - 123456
образ Ubuntu login - student, password - 123456
В случае если диск с таким-же  UUID существует, смените его, введя команду в консоли, и изменив (UUID 799e63d3-3be6-465e-ad7f-fe36430744d2)

E:\g1221>"C:\Program Files\Oracle\VirtualBox\VBoxManage" internalcommands sethduuid fedora19-edu.vdi 799e63d3-3be6-465e-ad7f-fe36430744d2 

Поясняющая информация
Команды POSIX для работы с ФС и дисками (должны быть во всех операционных системах)

df - выводит информацию о подмонтированных дисках

 

 

Команды и конфигурационные файлы в LINUX

fdformat - форматирование гибкого диска

mformat - создает файловую систему MS-DOS

fsck - проверка файловой системы

mkfs (mkfs.ext3, mkfs.btrfs и т.д.)  - создание файловой системы (форматирование)

В образе виртуальной машины не достает некоторых пакетов, например, для создания файловых систем XFS, NTFS, FAT. Необходимо установить пакеты: xfsprogs, ntfsprogs, dosfstools (используя yum,  или скачать с mirror.yandex.ru)

mkswap - создание раздела подкачки

swapon - активизация раздела подкачки

fdisk - работа с разделами диска при использовании MBR

gdisk -  работа с разделами диска при использовании GPT

parted - работа с разделами диска при использовании GPT и не только
 
mount - монтирование файловых систем

umount - размонтирование файловых систем

df - выводит информацию о подмонтированных дисках

/etc/fstab - файл для описания подключаемых файловых систем

debugfs -  востановление и получение подробной информации файловых систем

dumpe2fs -  получение подробной информации файловых систем

filefrag - получить информацию о фрагментации файла 

ntfsinfo - получение подробной информации о файловой системе NTFS

fsck.fat (-v)- получение подробной информации о файловой системе FAT

xfs_info - получение подробной информации о файловой системе XFS

btrfs-show-super - получение подробной информации о файловой системе BTRFS

 

Для получения более подробной информации, можно использовать help (например: ps --help), или документацию (например: man ps, для выхода нажмите q).

Некоторые комбинации клавиш:

<Ctrl+Z> - приостановить выполнение задания

<Ctrl+C> - завершить выполнение задания

Связывание процессов с помощью каналов. Запуск нескольких команд с передачей выходного потока следующей программе, "|" означает передачу выходного потока от первой программы ко второй.

ps -ax | more

запускается команда ps -ax, и передает выходной поток программ more которая запускается на выполнение.

Перенаправление ввода/вывода. Запуск команды с записью выходного потока в файл

ps -ax > test.txt

ps -ax > test.txt - добавит в коней файла

Группы команд

command-1;command-2;command-3

{command-1;command-2} > test.txt

Задание:

Что нужно уметь:
- монтировать/размонтировать файловую систему 
- выводить информацию о подмонтированных дисках (чтобы было видно тип файловой системы) 
- создавать файловые системы (форматирование) 
- создавать разделы
- проверять файловые системы 
В своей виртуальной машине сделать:
- создать виртуальный диск (скриншот доступных дисков в отчет)
- на этом диске создать 8 разделов (размером N Мбайт, N-последние три цифры в номере зачетки) используя MBR запись (не GPT)  (скриншот доступных разделов на диске в отчет)
- на одном из разделов создать файловую систему NTFS (размер блока (байт) (256) 1024, 2048, 4096 (65536) самый близкий размер к последней цифре в номере зачетки)  (скриншоты команды форматирования и информации о файловой системе в отчет)
- на одном из разделов создать файловую систему FAT32  (скриншоты команды форматирования и информации о файловой системе в отчет)
- на одном из разделов создать файловую систему EXT2 (размер блока (байт) 1024, 2048, 4096 самый близкий размер к последней цифре в номере зачетки)  (скриншоты команды форматирования и информации о файловой системе в отчет)
- на одном из разделов создать файловую систему EXT3, включить журналирование данных (не только метаданных) (размер блока (байт) 1024, 2048, 4096 самый близкий размер к последней цифре в номере зачетки) (скриншоты команды форматирования и информации о файловой системе в отчет)
- на одном из разделов создать файловую систему EXT4, включить журналирование данных (не только метаданных) (размер блока (байт) 1024, 2048, 4096 самый близкий размер к последней цифре в номере зачетки) (скриншоты команды форматирования и информации о файловой системе в отчет)
- на одном из разделов создать файловую систему Btrfs (скриншоты команды форматирования и информации о файловой системе в отчет)
- на одном из разделов создать файловую систему xfs (скриншоты команды форматирования и информации о файловой системе в отчет)
- монтировать все разделы в подкаталоги каталога /mnt/фамилия/название файловой системы (скриншот подмонтированных разделов с колонкой "тип файловой системы" в отчет)
- сделать автоматическое монтирование при загрузке, используя UUID дисков (скриншот fstab в отчет)
- на одном из разделов создать файловую систему для SWAP (скриншот разделов на диске в отчет)
- выполните проверку раздела с файловой системой EXT2  (скриншот результата проверки в отчет)
Изучить теорию: Диски и файловые системы (сектор,MBR,разделы, блоки, кластеры, суперблок, процесс загрузки системы).
 

 


При сдаче: 

умение работать с этими командами.
выполненные задания на виртуальных машинах
Рассказать: Диски и файловые системы (сектор,MBR,разделы, блоки, кластеры, суперблок, процесс загрузки системы).
