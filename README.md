## HW5-ZFS  
Практические навыки работы с ZFS  
Используем методичку практические навыки работы с ZFS https://docs.google.com/document/d/1xursgUsGDVTLh4B_r0XGw_flPzd5lSJ0nfMFL-HQmFs/edit?usp=share_link   
Используем ![Vagrant-файл](./Vagrantfile) для развёртывания нашего стенда  
### 1. Определить алгоритм с наилучшим сжатием  
Определить какие алгоритмы сжатия поддерживает zfs (gzip, zle, lzjb, lz4);  
Создать 4 файловых системы, на каждой применить свой алгоритм сжатия;  
Команды и их вывод в терминал - в файле ![typescript1](./typescript1)  
Видно, что алгоритм gzip-9 самый эффективный по сжатию.  
### 2. Определение настроек пула  
С помощью команды zfs import собрать pool ZFS;  
Командами zfs определить настройки:  
- размер хранилища;  
- тип pool;  
- значение recordsize;  
- какое сжатие используется;  
- какая контрольная сумма используется.  
Команды и их вывод в терминал - в файле ![typescript2](./typescript2)  
Получаем для наших настроек:
- available 350M;  
- readonly off (чтение и запись);  
- recordsize 128K;  
- compression zle;  
- checksum sha256.  
### 3. Работа со снапшотом, поиск сообщения от преподавателя  
Скопировать файл из удаленной директории;  
Восстановить файл локально - zfs receive;  
Найти зашифрованное сообщение в файле secret_message.  
Команды и их вывод в терминал - в файле ![typescript3](./typescript3)  
В содержимом найденного файла видим ссылку на GitHub: https://github.com/sindresorhus/awesome  
### 4. Заметки по ходу выполнения работы (не относятся непосредственно к теме самой работы, просто, с чем пришлось столкнуться)  
Решение проблем, связанных с установкой VBox Guest Additions: https://superuser.com/questions/412527/modprobe-vboxguest-failed  
И ещё: https://linuxconfig.org/install-virtualbox-guest-additions-on-linux-guest - чтобы нормально обмениваться файлами с виртуалкой, кроме всего прочего  
Примеры использования команды mount и umount: https://wiki.dieg.info/mount  
Вариант подмонтирования ntfs: https://svennd.be/mount-unknown-filesystem-type-ntfs-on-centos-7-2/  
Скачать файл с google диска через wget (иногда не качается на виртуалку/linux-машину): https://amorev.ru/skachat-fajl-s-google-diska-cherez-wget/  
