---
## Front matter
title: "Отчёта по лабораторной работе №1"
subtitle: "Установка и конфигурация
операционной системы на виртуальную машину"
author: "Ван Сихэм Франклин О Нил Джон (Миша)"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt

## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english

## I18n babel
babel-lang: russian
babel-otherlangs: english

## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:

## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric

## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"

## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью данной работы является приобретение практических навыков установки опера-
ционной системы на виртуальную машину, настройки минимально необходимых для
дальнейшей работы сервисов.


# Задание

Здесь приводится описание задания в соответствии с рекомендациями
методического пособия и выданным вариантом.

# Теоретическое введение

Здесь описываются теоретические аспекты, связанные с выполнением работы.

Например, в табл. [-@tbl:std-dir] приведено краткое описание стандартных каталогов Unix.

: Описание некоторых каталогов файловой системы GNU Linux {#tbl:std-dir}

| Имя каталога | Описание каталога                                                                                                          |
|--------------|----------------------------------------------------------------------------------------------------------------------------|
| `/`          | Корневая директория, содержащая всю файловую                                                                               |
| `/bin `      | Основные системные утилиты, необходимые как в однопользовательском режиме, так и при обычной работе всем пользователям     |
| `/etc`       | Общесистемные конфигурационные файлы и файлы конфигурации установленных программ                                           |
| `/home`      | Содержит домашние директории пользователей, которые, в свою очередь, содержат персональные настройки и данные пользователя |
| `/media`     | Точки монтирования для сменных носителей                                                                                   |
| `/root`      | Домашняя директория пользователя  `root`                                                                                   |
| `/tmp`       | Временные файлы                                                                                                            |
| `/usr`       | Вторичная иерархия для данных пользователя                                                                                 |

Более подробно про Unix см. в [@tanenbaum_book_modern-os_ru; @robbins_book_bash_en; @zarrelli_book_mastering-bash_en; @newham_book_learning-bash_en].

# Выполнение лабораторной работы

![Рис. 1.1. Окно «Имя и операционная система виртуальной машины», путь к iso-образу](image/image1.jpg){#fig:001 width=70%}


![Рис. 1.2. Окно «Оборудование»](image/image2.jpg){#fig:001 width=70%}


![Рис. 1.3. Окно «Виртуальный жёсткий диск»](image/image3.jpg){#fig:001 width=70%}

![Рис. 1.4. Запуск установки виртуальной машины](image/image5.jpg){#fig:001 width=70%}

![Рис. 1.5. Установка английского языка интерфейса ОС](image/image6.jpg){#fig:001 width=70%}

![Рис. 1.6. Окно настройки установки: выбор программ](image/image7.jpg){#fig:001 width=70%}

![Рис. 1.7. Окно настройки установки: отключение KDUMP](image/image8.jpg){#fig:001 width=70%}

![Рис. 1.8. Окно настройки установки: место установки](image/image9.jpg){#fig:001 width=70%}

![Рис. 1.9. Окно настройки установки: сеть и имя узла](image/image10.jpg){#fig:001 width=70%}

![Рис. 1.10. Установка пароля для root](image/image11.jpg){#fig:001 width=70%}

![Рис. 1.11. Установка пароля для пользователя с правами администратора](image/image12.jpg){#fig:001 width=70%}

![Рис. 1.12. Окно настройки установки образа ОС](image/image13.jpg){#fig:001 width=70%}

![Рис. 1.13. Завершение установки ОС](image/image14.jpg){#fig:001 width=70%}

![Рис. 1.14. Подключение образа диска дополнений гостевой ОС](image/image15.jpg){#fig:001 width=70%}


После загрузки дополнений нажмите Return или Enter и корректно перезагрузите вир-
туальную машину.
Если по каким-то причинам образ диска дополнений гостевой ОС не уста-
навливается через графическое меню, можно воспользоваться консольными
командами (рис. 1.16). Войдите в ОС под заданной вами при установке учёт-
ной записью пользователя, получите полномочия администратора, перейдите
в каталог /run/media/имя_пользователя/VBox_GAs_версия/, затем запустите
VBoxLinuxAdditions.run:
	
	sudo -i
	
	cd /run/media/имя_пользователя/VBox_GAs_версия/.VBoxLinuxAdditions.run

![Рис. 1.15. Подключение образа диска дополнений гостевой ОС через консольные команды](image/image16.jpg){#fig:001 width=70%}

## Установка имени пользователя и названия хоста

Если при установке виртуальной машины вы задали имя пользователя или имя хоста, не удовлетворяющее соглашению об именовании (см. раздел 1.2.2), то вам необходимо исправить это.
1. Запустите виртуальную машину и залогиньтесь.
2. Запустите терминал и получите полномочия администратора:
	
	```
	sudo -i
	```

3. Создайте пользователя (вместо username укажите ваш логин в дисплейном классе):

	```
	adduser -G wheel username
	```

4. Задайте пароль для пользователя (вместо username укажите ваш логин в дисплейном классе):
	
	```
	passwd username
    ```

5. Установите имя хоста (вместо username укажите ваш логин в дисплейном классе):
	
	```
	hostnamectl set-hostname username
	```

6. Проверьте, что имя хоста установлено верно:
	
	```
	hostnamectl
	```

![Рис. 1.16. Установка имени пользователя и названия хоста](image/image17.jpg){#fig:001 width=70%}


## Домашнее задание


# Выводы

Здесь кратко описываются итоги проделанной работы.

# Список литературы{.unnumbered}

::: {#refs}
:::
