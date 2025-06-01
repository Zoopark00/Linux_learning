# Linux_learning
##Занятие 1. Обновление ядра системы##
1. parallels@ubuntu-linux-2404:~$ uname -r
- 6.8.0-40-generic
2. parallels@ubuntu-linux-2404:~$ uname -p
- aarch64
3. parallels@ubuntu-linux-2404:~$ mkdir kernal && cd kernal
4. parallels@ubuntu-linux-2404:~/kernal$ wget https://kernel.ubuntu.com/mainline/v6.14.6/arm64/linux-headers-6.14.6-061406-generic_6.14.6-061406.202505090840_arm64.deb
5. parallels@ubuntu-linux-2404:~/kernal$ wget https://kernel.ubuntu.com/mainline/v6.14.6/arm64/linux-image-unsigned-6.14.6-061406-generic_6.14.6-061406.202505090840_arm64.deb
6. parallels@ubuntu-linux-2404:~/kernal$ wget https://kernel.ubuntu.com/mainline/v6.14.6/arm64/linux-modules-6.14.6-061406-generic_6.14.6-061406.202505090840_arm64.deb
parallels@ubuntu-linux-2404:~/kernal$ dpkg -i *.deb
###При установке пакетов ядра вылезли ошибки###
- pkg: error processing package linux-headers-6.14.6-061406-generic (--install):
- dependency problems - leaving unconfigured
###При перезагрузке система упала в kernal panic.###
- Пришлось вернуться к старому ядру и выполнить команду для подгрузки зависисостей
7. parallels@ubuntu-linux-2404:~/kernal$ sudo apt --fix-broken install
8. parallels@ubuntu-linux-2404:~/kernal$ sudo update-grub
###После этого система поднялась корректно с новым ядром:###
9. parallels@ubuntu-linux-2404:~$ uname -r
- 6.14.6-061406-generic

