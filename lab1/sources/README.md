# CMD

- [x] [Создаём диск R](#создаём-диск-r)
- [x] [Задание 1](#задание-1)
- [x] [Задание 2](#задание-2)
- [ ] [Задание 3](#задание-3)
- [ ] [Задание 4](#задание-4)
- [ ] [Задание 5](#задание-5)
- [x] [Задание 6](#задание-6)
- [x] [Задание 7](#задание-7)
- [ ] [Задание 8](#задание-8)
- [ ] [Задание 9](#задание-9)
- [ ] [Задание 10](#задание-10)
- [ ] [Задание 11](#задание-11)
- [ ] [Задание 12](#задание-12)
- [ ] [Задание 13](#задание-13)
- [ ] [Задание 14](#задание-14)
- [ ] [Задание 15](#задание-15)
- [ ] [Задание 16](#задание-16)
- [x] [Задание 17](#задание-17)
- [ ] [Задание 18](#задание-18)
- [ ] [Задание 19](#задание-19)
- [ ] [Задание 20](#задание-20)
- [x] [Задание 21](#задание-21)
- [x] [Задание 22](#задание-22)
- [x] [Задание 23](#задание-23)
- [x] [Задание 24](#задание-24)
- [x] [Задание 25](#задание-25)
- [x] [Задание 26](#задание-26)
- [x] [Задание 27](#задание-27)
- [ ] [Задание 28](#задание-28)

## Создаём диск R

1. `Win` + `E`.
2. Левой кнопкой пиши по `This computer`.
3. `Manager`.
4. `Computer Managment (Local)` > `Storage` > `Disk Managment`.
5. Левой кнопкой мыши по диску.
6. `Shrink volume`.
7. Enter the amount of space to thrink in MB: `1024`.
8. Жмём `Shrink`.
9. Жмём левой кнопкой мыши по пустому пространству.
10. `New Simple Volume...`.
11. `Next >`.
12. Simple volume size in MB: `1024`.
13. `Next >`.
14. Assing the following drive letter: `R`.
15. `Next >`.
16. Volume label: `R`.
15. `Next >`.
15. `Finish`.

## Задание 1

Создайте на диске `R:\` файл `R:\test3.txt` и каталог `R:\LAB`,
в каталоге `R:\LAB` создайте файлы `file1`, `file2`, `file3` и `file4.txt`, `file5.txt`, `file6.txt`.
Выведите атрибуты файла `R:\test3.txt`.
Назначьте атрибут «Только чтение» файлу `R:\test3.txt`.
Удалите атрибут "Только чтение" для всех файлов из папки `R:\LAB\` с расширением `*.txt`.
Отмените атрибут "Только чтение" для всех файлов в каталоге `R:\LAB\`.
Установите атрибут «Архивный» для всех файлов на диске `R:\`.

```
r:

REM Создаём файл R:\test3.txt
copy con test3.txt
REM Вводим текст
REM Жмём Ctrl + Z
REM Результат: Содержимое для файла тест 3
REM Результат: Сожержимое для файла тест 3^Z
REM Результат:         1 file(s) copied.


REM Создаём каталог R:\LAB
mkdir LAB


REM Проверяем
dir
REM Результат:  Volume in drive R is R
REM Результат:  Volume Serial Number is 92FB-194A
REM Результат: 
REM Результат:  Directory of R:\
REM Результат: 
REM Результат: 06/04/2022  12:33 AM    <DIR>          LAB
REM Результат: 06/04/2022  12:30 AM                56 test3.txt
REM Результат:                1 File(s)             56 bytes
REM Результат:                1 Dir(s)   1,058,406,400 bytes free
```

```cmd
REM Создаю файл
copy con LAB\file1.txt
REM Результат: content for file 1^Z
REM Результат:         1 file(s) copied.

REM Создаю файл
copy con LAB\file2.txt  
REM Результат: content for file 2^Z
REM Результат:         1 file(s) copied.

REM Создаю файл
copy con LAB\file3.txt  
REM Результат: content for file 3^Z
REM Результат:         1 file(s) copied.

REM Создаю файл
copy con LAB\file4.txt  
REM Результат: content for file 4^Z
REM Результат:         1 file(s) copied.

REM Создаю файл
copy con LAB\file5.txt  
REM Результат: content for file 5^Z
REM Результат:         1 file(s) copied.

REM Создаю файл
copy con LAB\file6.txt  
REM Результат: content for file 6^Z
REM Результат:         1 file(s) copied.


type LAB\file1.txt
REM Результат: content for file 1

type LAB\file2.txt
REM Результат: content for file 2

type LAB\file3.txt
REM Результат: content for file 3

type LAB\file4.txt
REM Результат: content for file 4

type LAB\file5.txt
REM Результат: content for file 5

type LAB\file6.txt
REM Результат: content for file 6
```

```cmd
attrib test3.txt
REM Результат: A                    R:\test3.txt

REM Назначаю атрибут «Только чтение» файлу R:\test3.txt
attrib -a +r test3.txt

attrib test3.txt
REM Результат:      R               R:\test3.txt
```

```cmd
attrib LAB\*
REM Результат: A                    R:\LAB\file1.txt
REM Результат: A                    R:\LAB\file2.txt
REM Результат: A                    R:\LAB\file3.txt
REM Результат: A                    R:\LAB\file4.txt
REM Результат: A                    R:\LAB\file5.txt
REM Результат: A                    R:\LAB\file6.txt

attrib +r LAB\*

attrib LAB\*    
REM Результат: A    R               R:\LAB\file1.txt
REM Результат: A    R               R:\LAB\file2.txt
REM Результат: A    R               R:\LAB\file3.txt
REM Результат: A    R               R:\LAB\file4.txt
REM Результат: A    R               R:\LAB\file5.txt
REM Результат: A    R               R:\LAB\file6.txt

REM Удаляю атрибут "Только чтение" для всех файлов из папки R:\LAB\ с расширением *.txt
attrib -r LAB\*.txt

attrib LAB\*    
REM Результат: A                    R:\LAB\file1.txt
REM Результат: A                    R:\LAB\file2.txt
REM Результат: A                    R:\LAB\file3.txt
REM Результат: A                    R:\LAB\file4.txt
REM Результат: A                    R:\LAB\file5.txt
REM Результат: A                    R:\LAB\file6.txt
```

```
attrib /s
REM Результат: A  SH                R:\$RECYCLE.BIN\S-1-5-21-1572068156-799976528-1259778827-1001\desktop.ini
REM Результат: A                    R:\LAB\file1.txt
REM Результат: A                    R:\LAB\file2.txt
REM Результат: A                    R:\LAB\file3.txt
REM Результат: A                    R:\LAB\file4.txt
REM Результат: A                    R:\LAB\file5.txt
REM Результат: A                    R:\LAB\file6.txt
REM Результат:      R               R:\test3.txt


attrib /s -a
REM Результат: Not resetting hidden file - R:\$RECYCLE.BIN\S-1-5-21-1572068156-799976528-1259778827-1001\desktop.ini


attrib /s
REM Результат: A  SH                R:\$RECYCLE.BIN\S-1-5-21-1572068156-799976528-1259778827-1001\desktop.ini
REM Результат:                      R:\LAB\file1.txt
REM Результат:                      R:\LAB\file2.txt
REM Результат:                      R:\LAB\file3.txt
REM Результат:                      R:\LAB\file4.txt
REM Результат:                      R:\LAB\file5.txt
REM Результат:                      R:\LAB\file6.txt
REM Результат:      R               R:\test3.txt


attrib /s
REM Результат: A  SH                R:\$RECYCLE.BIN\S-1-5-21-1572068156-799976528-1259778827-1001\desktop.ini
REM Результат:                      R:\LAB\file1.txt
REM Результат:                      R:\LAB\file2.txt
REM Результат:                      R:\LAB\file3.txt
REM Результат:                      R:\LAB\file4.txt
REM Результат:                      R:\LAB\file5.txt
REM Результат:                      R:\LAB\file6.txt
REM Результат:      R               R:\test3.txt


REM Устанавливаю атрибут «Архивный» для всех файлов на диске R:\
attrib /s +a
REM Результат: Not resetting hidden file - R:\$RECYCLE.BIN\S-1-5-21-1572068156-799976528-1259778827-1001\desktop.ini


attrib /s    
REM Результат: A  SH                R:\$RECYCLE.BIN\S-1-5-21-1572068156-799976528-1259778827-1001\desktop.ini
REM Результат: A                    R:\LAB\file1.txt
REM Результат: A                    R:\LAB\file2.txt
REM Результат: A                    R:\LAB\file3.txt
REM Результат: A                    R:\LAB\file4.txt
REM Результат: A                    R:\LAB\file5.txt
REM Результат: A                    R:\LAB\file6.txt
REM Результат: A    R               R:\test3.txt
```

## Задание 2

Просмотрите текущую кодовую страницу.
Замените текущую кодовую страницу страницей «Восточная и центральная Европа»
затем на «Французский (Канада)».
Верните первоначальную кодовую страницу.

```cmd
REM Смотрим текущую кодовую страницу
chcp
REM Результат: Active code page: 437


REM Заменяем текущую кодовую страницу страницей «Восточная и центральная Европа»
chcp 852
REM Результат: Active code page: 852

REM Смотрим текущую кодовую страницу
chcp
REM Результат: Active code page: 852


REM Заменяем текущую кодовую страницу на «Французский (Канада)»
chcp 863
REM Результат: Active code page: 863

REM Смотрим текущую кодовую страницу
chcp
REM Результат: Active code page: 863


REM Возвращаем первоначальную кодовую страницу
chcp 437
REM Результат: Active code page: 437

REM Смотрим текущую кодовую страницу
chcp
REM Результат: Active code page: 437
```

## Задание 3

Создайте на диске `R:\` каталог и подкаталог (`R:\SUB1\SUB2\`).
Перейдите в каталог `SUB1`,
а затем в подкаталог текущего каталога.
Перейдите из подкаталога в родительский каталог.
Выведите на экран имя текущего каталога.
В каталоге `R:\SUB1` создайте файлы `file1`, `file2`, `file3` и `file4.txt`, `file5.txt`, `file6.txt`.
Скопируйте все файлы каталога `R:\SUB1` на корневой диск `R:\`.

## Задание 4

Проверьте диск в дисководе `R:\` и исправить все обнаруженные ошибки.

## Задание 5

Проверьте, зашифрована ли папка `R:\SUB1`.
Создайте каталог `R:\SUB3\` и файл `R:\SUB3\lab.txt`, зашифруйте данный файл, зашифруйте папку `R:\SUB3`.

## Задание 6

Очистите окно командной строки.

```
cls
```

## Задание 7

Изменить цвет текста на красный, а цвет фона на зеленый.

```
color 24
```

## Задание 8

Сравнить первые 5 строк двух файлов в каталоге `R:\SUB1` и вывести результат в десятичном формате.
Сравнить первые 10 строк двух файлов в каталоге `R:\SUB1` и вывести номера строк в которых встретились различия.

## Задание 9

Создайте, используя консольный ввод файлы `R:\Memo.doc` и `R:\Memo1.doc`.
Для создания файла в командной строке используется команда `copy con имя_файла`.
После того, как выполнили командe `copy con имя_файла` необходимо напечатать текст (содержимое файла),
а затем завершить ввод нажатием `Ctrl + Z`.
Скопируйте файл `Memo.doc` в файл `Letter.doc` на текущем диске и убедитесь,
что символ конца файла находится в конце скопированного файла.
Скопируйте несколько файлов в один `R:\Memo.doc` и `R:\Memo1.doc` в `R:\Result.txt`
(организуйте проверку правильности копирования путем сравнения копий файлов).

## Задание 10

Задайте кодовую страницу вместе с кодом страны для Польши.

## Задание 11

Выведите текущую системную дату и измените ее.

## Задание 12

Вывести подряд все каталоги диска `C:\` в алфавитном порядке,
в несколько колонок и с паузой после заполнения каждого экрана.
Вывести все каталоги диска `C:\` с сортировкой по дате и времени от ранних к поздним.
Вывести все файлы диска `C:\` с сокращенными именами файлов.
Организуйте перенаправление вывода содержимого корневого диска `С:\` в файл `Dr.txt` в каталоге `R:\SUB2\`.

## Задание 13

Сравните два текстовых файла с именами `Monthly.rpt` и `Sales.rpt` и выведите результат в сокращенном формате.
Сравните два текстовых файла с именами `Monthly.rpt` и `Sales.rpt` и выведите результат в двоичном формате.

## Задание 14

Создайте файл `R:\TEXT_MY`, содержащий осмысленный текст.
Создайте файл `R:\DTEXT`, содержащий дважды продублированный текст из файла `R:\TEXT_MY`.
Организуйте поиск любого слова из файла `R:\TEXT_MY`, проанализируйте результат.

## Задание 15

Продублируйте 10 раз содержимое файла `R:\TEXT_MY`, результат сохраните в файл `R:\Big.txt`.
Организуйте по экранный вывод информации из файла `R:\Big.txt`.

## Задание 16

Переместить все файлы с расширением `.txt` из каталога `R:\SUB1` в каталог `R:\SUB2`.

## Задание 17

Для диска `C:\` выведите текущие пути поиска исполняемых файлов.

```cmd
REM Выводим пути поиска исполняемых файлов для диска C:\
c:
cd c:\
echo %path%
REM Результат: C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Windows\System32\OpenSSH\;C:\MyApps\MicrosoftVSCode\bin;C:\MyApps\Git\cmd;C:\Users\gpi_\AppData\Local\Microsoft\WindowsApps;  
```

## Задание 18

Измените приглашение командной строки на

```
Текущее время| Текущая дата $Текущий диск=
```

## Задание 19

Создайте файл `Story.txt` на диске `R:\` в каталоге `\SUB1`.
Выведите содержимое текстового файла `Story.txt` на экран Удалите файл `Story.txt`.
Попытайтесь восстановить файл `Story.txt` из каталога `R:\SUB1`.

## Задание 20

Выведите и измените связи между расширениями имени типами для файлов `R:\test1.txt`, `R:\test2.txt`.
Удалите тип файла, соответствующий расширению имени файла `R:\test2.txt`.
Просмотрите текущие сопоставления типов файлов.
Отправьте результаты выполнения предыдущей команды в файл `Result.cfg`

## Задание 21

Выведите на экран подробные сведения о конфигурации компьютера и операционной системы,
сведения о безопасности, код продукта и параметры оборудования, такие как ОЗУ, дисковое пространство и сетевые карты.

```cmd
REM Выводим подробные сведения о конфигурации компьютера и операционной системы,
REM код продукта и параметры оборудования, такие как ОЗУ,
REM дисковое пространство и сетевые карты
systeminfo
REM Результат: 
REM Результат:  Host Name:                 ASPIRE3
REM Результат:  OS Name:                   Microsoft Windows 10 Home
REM Результат:  OS Version:                10.0.19044 N/A Build 19044
REM Результат:  OS Manufacturer:           Microsoft Corporation
REM Результат:  OS Configuration:          Standalone Workstation
REM Результат:  OS Build Type:             Multiprocessor Free
REM Результат:  Registered Owner:          gpi_
REM Результат:  Registered Organization:
REM Результат:  Product ID:                00326-10000-00000-AA770
REM Результат:  Original Install Date:     6/3/2022, 10:13:51 PM
REM Результат:  System Boot Time:          6/4/2022, 3:31:56 AM
REM Результат:  System Manufacturer:       Acer
REM Результат:  System Model:              Aspire A315-23
REM Результат:  System Type:               x64-based PC
REM Результат:  Processor(s):              1 Processor(s) Installed.
REM Результат:                             [01]: AMD64 Family 23 Model 24 Stepping 1 AuthenticAMD ~1700 Mhz
REM Результат:  BIOS Version:              Insyde Corp. V1.06, 4/27/2020
REM Результат:  Windows Directory:         C:\Windows
REM Результат:  System Directory:          C:\Windows\system32
REM Результат:  Boot Device:               \Device\HarddiskVolume1
REM Результат:  System Locale:             en-us;English (United States)
REM Результат:  Input Locale:              en-us;English (United States)
REM Результат:  Time Zone:                 (UTC-08:00) Pacific Time (US & Canada)
REM Результат:  Total Physical Memory:     3,521 MB
REM Результат:  Available Physical Memory: 1,604 MB
REM Результат:  Virtual Memory: Max Size:  4,865 MB
REM Результат:  Virtual Memory: Available: 2,485 MB
REM Результат:  Virtual Memory: In Use:    2,380 MB
REM Результат:  Page File Location(s):     C:\pagefile.sys
REM Результат:  Domain:                    WORKGROUP
REM Результат:  Logon Server:              \\ASPIRE3
REM Результат:  Hotfix(s):                 4 Hotfix(s) Installed.
REM Результат:                             [01]: KB5004331
REM Результат:                             [02]: KB5003791
REM Результат:                             [03]: KB5006670
REM Результат:                             [04]: KB5005699
REM Результат:  Network Card(s):           2 NIC(s) Installed.
REM Результат:                             [01]: Realtek PCIe GbE Family Controller
REM Результат:                                   Connection Name: Ethernet
REM Результат:                                   Status:          Media disconnected
REM Результат:                             [02]: Qualcomm Atheros QCA9377 Wireless Network Adapter
REM Результат:                                   Connection Name: Wi-Fi
REM Результат:                                   Status:          Media disconnected
REM Результат:  Hyper-V Requirements:      VM Monitor Mode Extensions: Yes
REM Результат:                             Virtualization Enabled In Firmware: Yes
REM Результат:                             Second Level Address Translation: Yes
REM Результат:                             Data Execution Prevention Available: Yes
```

## Задание 22

Выведите системное время.

```cmd
REM Вводим новое системное время
time
REM Резултьтат: Enter the new time:
REM Вводим 0
REM Резултьтат: A required privilege is not held by the client.
REM У нас нет прав администратора


REM Заходим в CMD с правами администратора
REM Вводим новое системное время
time
REM Резултьтат: The current time is:  3:43:44.43
REM Резултьтат: Enter the new time:
REM Вводим 0


echo %time%
REM Резултьтат: 0:00:12.68
```

## Задание 23

Организуйте вывод графического дерево каталога `С:\`.

```cmd
REM Выводим графическое дерево каталога C:\
tree C:\
REM Результат: Folder PATH listing
REM Результат: Volume serial number is 0000000A E85A:BD9A
REM Результат: C:.
REM Результат: ├───MyApps
REM Результат: │   ├───Git
REM Результат: │   │   ├───bin
REM Результат: │   │   ├───cmd
REM Результат: │   │   ├───dev
REM Результат: │   │   │   ├───mqueue
REM Результат: │   │   │   └───shm
REM Результат: │   │   ├───etc
REM Результат: │   │   │   ├───pkcs11
REM Результат: │   │   │   ├───pki
REM Результат: │   │   │   │   └───ca-trust
REM Результат: │   │   │   │       └───extracted
REM Результат: │   │   │   │           ├───java
REM Результат: │   │   │   │           ├───openssl
REM Результат: │   │   │   │           └───pem
REM Результат: │   │   │   ├───profile.d
REM Результат: │   │   │   └───ssh
REM Результат: │   │   ├───mingw64
REM Результат: │   │   │   ├───bin
REM Результат: │   │   │   ├───doc
REM Результат: │   │   │   │   └───git-credential-manager
```

## Задание 24

Выведите версию операционной системы.

```cmd
REM Выводим версию операционной системы в графическом окне
winver


REM Выводим версию операционной системы в консоль
ver
REM Результат: Microsoft Windows [Version 10.0.19044.1288]
```

## Задание 25

Выведите метку тома диска `С:\` и серийный номер.

```cmd
REM Выводим метку тома C:\ и серийный номер
vol c:
REM Результат: Volume in drive C has no label.
REM Результат: Volume Serial Number is E85A-BD9A
```

## Задание 26

Получите MAC-адреса сетевой карты

```cmd
REM Получаем MAC-адреса сетевой карты
getmac
REM Результат: Physical Address    Transport Name
REM Результат: =================== ==========================================================
REM Результат: BB-BB-BB-BB-BB-BB   Media disconnected
REM Результат: BB-BB-BB-BB-BB-BB   \Device\Tcpip_{BBBBBBBB-BBBB-BBBB-BBBB-BBBBBBBBBBBB}
```

## Задание 27

Узнайте текущий IP-адрес, шлюз, DNS и т.п.

```cmd
REM Узнаём текущий IP-адрес
ipconfig
REM Результат: 
REM Результат: Windows IP Configuration
REM Результат: 
REM Результат: 
REM Результат: Ethernet adapter Ethernet:
REM Результат: 
REM Результат:    Media State . . . . . . . . . . . : Media disconnected
REM Результат:    Connection-specific DNS Suffix  . : 
REM Результат: 
REM Результат: Wireless LAN adapter Local Area Connection* 1:
REM Результат: 
REM Результат:    Media State . . . . . . . . . . . : Media disconnected
REM Результат:    Connection-specific DNS Suffix  . : 
REM Результат: 
REM Результат: Wireless LAN adapter Local Area Connection* 2:
REM Результат: 
REM Результат:    Media State . . . . . . . . . . . : Media disconnected
REM Результат:    Connection-specific DNS Suffix  . :
REM Результат: 
REM Результат: Wireless LAN adapter Wi-Fi:
REM Результат: 
REM Результат:    Connection-specific DNS Suffix  . :
REM Результат:    Link-local IPv6 Address . . . . . : fe80::459:4af5:fa9f:726a%17
REM Результат:    IPv4 Address. . . . . . . . . . . : 192.168.100.5
REM Результат:    Subnet Mask . . . . . . . . . . . : 255.255.255.0
REM Результат:    Default Gateway . . . . . . . . . : fe80::1%17
REM Результат:                                        192.168.100.1
```

## Задание 28

Выведите сетевой адрес.

<!--
Содержимое отчета

1. Титульный лист
2. Цель работы
3. Полный формат команд по каждому пункту задания и результаты выполнения команд
   (скриншот экрана (скриншот - это точное изображение того,
   что вы видите на экране монитора в данный момент)
   после выполнения каждой команды).
4. Вывод
-->
