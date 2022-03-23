# Backend cheats

Данный репозиторий представляет собой наглядную шпаргалку по основным темам в области Backend-разработки. Весь материал разбит на темы и подтемы. Структура материала состоит из 3 частей:

-   **Визуальная часть** - различные изображения/таблицы/шпаргалки для лучшего понимания (может отсутствовать). Все рисунки и таблицы сделаны с нуля, специально для этого репозитория.
-   **Краткое описание** - очень краткая выжимка информации с перечнем основных терминов и понятий. На все термины навешиваются гиперссылки ведущие на соответсвующий раздел в Википедии.
-   **Ссылки на источники** - ресурсы, где можно найти полную информацию по конкретному вопросу. По возможности мы стараемся указывать максимально авторитетные источники, либо же те, которые предоставляют информацию максимально простым и понятным языком.

Изучать материал можно последовательно шаг за шагом.

> 🛠 Репозиторий находится в стадии активной разработки, поэтому постоянно обновляется и дополняется

> 🤝 Если вы хотите помочь проекту, не стесняйтесь присылать свои пулл реквесты

> 📝 The translation into English will be start after all the main topics have been completed

<p><a name="top"></a></p>

## Содержание

-   [1. Сеть и интернет](#сеть-и-интернет)
    -   [Как устроен интернет](#как-устроен-интернет)
    -   [Что такое DNS](#что-такое-dns)
    -   [Что такое доменное имя](#что-такое-доменное-имя)
    -   [Браузеры и как они работают](#браузеры-и-как-они-работают)
    -   [Хостинг](#хостинг)
    -   [Cтек протоколов TCP/IP](#cтек-протоколов-tcpip)
    -   [Проблемы сети](#проблемы-сети)
    -   [IPv4 и IPv6](#ipv4-и-ipv6)
    -   [Трассировка маршрутов](#трассировка-маршрутов)
-   [2. Операционные системы](#операционные-системы)
    -   [Как работают ОС](#как-работают-ос)
    -   [Управление процессами](#управление-процессами)
    -   [Потоки и параллелизм](#потоки-и-параллелизм)
    -   [Управление памятью](#управление-памятью)
    -   [Межпроцессорное взаимодействие](#межпроцессорное-взаимодействие)
    -   [Ввод и вывод (I/O)](#ввод-и-вывод-io)
    -   [Основы POSIX](#основы-posix)
-   [3. Основы Linux](#основы-linux)
    -   [Работа с терминалом](#работа-с-терминалом)
    -   [Менеджер пакетов](#менеджер-пакетов)
    -   [Скрипты Bash](#скрипты-bash)
    -   [Пользователи](#пользователи)
    -   [Права доступа](#права-доступа)
    -   [Работа с процессами](#работа-с-процессами)
    -   [Работа с SSH](#работа-с-ssh)
    -   [Планировщик задач](#планировщик-задач)
    -   [Системные логи](#системные-логи)
    -   [Проблемы Linux](#проблемы-linux)

## Сеть и интернет

[Интернет](https://ru.wikipedia.org/wiki/%D0%98%D0%BD%D1%82%D0%B5%D1%80%D0%BD%D0%B5%D1%82) - это всемирная система объединяющая компьютерные сети со всего мира в единую сеть для хранения/передачи информации. Изначально Интернет разрабатывался для военных. Но вскоре он стал внедряться в учреждения образования (университеты), а затем его смогли использовать частные компании, которые начали организовывать сети провайдеров, предоставляющие услуги доступа в Интернет обычным гражданам. К началу 2020 года количество пользователей в сети Интернет перевалило за 4.5 млрд человек.

> **[История Интернета — Википедия](https://ru.wikipedia.org/wiki/%D0%98%D1%81%D1%82%D0%BE%D1%80%D0%B8%D1%8F_%D0%98%D0%BD%D1%82%D0%B5%D1%80%D0%BD%D0%B5%D1%82%D0%B0)**

-   ### Как устроен Интернет

    <p align="center"><img src="./files/network-internet/Internet.png" alt="Internet"/></p>

    Ваш компьютер никогда не был связан с Интернетом напрямую. Он видит только свою локальную сеть, в которую проводным (Ethernet) или беспроводным (Wi-Fi, Bluetooth) путем подключены другие устройства.
    Для связи с Интернетом в вашей локальной сети находиться специальный мини-компьютер - [маршрутизатор](https://ru.wikipedia.org/wiki/Маршрутизатор). Далее этот маршрутизатор связывает вас с интернет-провайдером, который в свою очередь связан с другими провайдерами более высокого уровня. Таким образом, ваше сообщение, пройдя транзитом через сеть нескольких провайдеров, достигнет сеть назначения.

    -   [Хост](https://ru.wikipedia.org/wiki/Хост)
        > _(host - принимающий)_ любое устройство, которое находится в какой-либо сети.
    -   [Сервер](<https://ru.wikipedia.org/wiki/Сервер_(аппаратное_обеспечение)>)
        > _(serve - обслуживать)_ специальный компьютер в сети, который обслуживает запросы поступающие от других компьютеров.

    > -   **[Как работает Интернет - MDN (mozilla.org)](https://developer.mozilla.org/ru/docs/Learn/Common_questions/How_does_the_Internet_work)**
    > -   **[Основы программирования. Как работают сети? - YouTube](https://www.youtube.com/watch?v=k_0BAtyaDio&ab_channel=Winderton)**
    > -   **[Хост — что это такое и как он работает](https://anisim.org/articles/host/)**
    > -   **[Что такое сервер и как он работает](https://timeweb.com/ru/community/articles/chto-takoe-server-i-kak-on-rabotaet)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Что такое DNS

    <p align="center"><img src="./files/network-internet/dns.png" alt="DNS"/></p>

    -   [DNS (Domain Name System)](https://ru.wikipedia.org/wiki/DNS)
        > Децентрализованная система именования адресов в Интернете, которая позволяет создавать удобные для человека буквеные наименования (доменные имена) соответствующие числовым IP-адресам, которые используются компьютерами.
    -   [IP-адрес](https://ru.wikipedia.org/wiki/IP-%D0%B0%D0%B4%D1%80%D0%B5%D1%81)
        > Специальный номерной идентификатор предоставляемый устройству находящемуся в какой-либо сети.

    > -   **[Система доменных имен DNS — YouTube](https://www.youtube.com/watch?v=B0J0c0KLtbQ&ab_channel=AndreySozykin)**
    > -   **[IP адрес — HackWare.ru](https://hackware.ru/?p=11589)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Что такое доменное имя

    <p align="center"><img src="./files/network-internet/Domain.png" alt="Domain"/></p>

    -   [Доменные имена](https://ru.wikipedia.org/wiki/%D0%94%D0%BE%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D0%B5_%D0%B8%D0%BC%D1%8F)
        > Человеко-читаемые адреса веб-серверов, доступных в Интернете. Они состоят из частей (уровней) разделенных между собой точкой. Каждая из этих частей предоставляет специфическую информацию о доменном имени. Например страну, название сервиса, локализацию и т.д.<br><br>

    > -   **[Что такое доменные имена - MDN (mozilla.org)](https://developer.mozilla.org/ru/docs/Learn/Common_questions/What_is_a_domain_name)**
    > -   **[Как работают домены](https://temoto.github.io/a/kak-rabotayut-domeny.html)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Браузеры и как они работают

    <p align="center"><img src="./files/network-internet/Browser.png" alt="Browser"/></p>

    -   [Браузер](https://ru.wikipedia.org/wiki/Браузер)
        > Клиент, с помощью которого можно отправлять запросы на сервер для получения файлов, которые впоследствии используются для отрисовки web-страниц. Большинство пользователей используют именно браузеры для работы в сети Интернет.

    > -   **[Как работают браузеры — MDN (mozilla.org)](https://developer.mozilla.org/ru/docs/Web/Performance/How_browsers_work)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Хостинг

    <p align="center"><img src="./files/network-internet/Hosting.png" alt="Hosting"/></p>

    -   [Хостинг (hosting)](https://ru.wikipedia.org/wiki/%D0%A5%D0%BE%D1%81%D1%82%D0%B8%D0%BD%D0%B3)
        > Специальная услуга, предоставляемая хостинг-провайдерами, которая позволяет арендовать пространство на сервере (который круглосуточно подключён к сети Интернет), где могут храниться ваши данные и файлы. Существуют различные варианты хостинга, где вы можете использовать не только дисковое пространство сервера, но и так же процессорную мощность для работы ваших сетевых приложений.

    > -   **[Хостинг: варианты, сравнения, пользовательская статистика — habr.com](https://habr.com/ru/company/ruvds/blog/443522/)**
    > -   **[Хостинг: что это, зачем и как выбрать – vc.ru](https://vc.ru/services/74241-hosting-chto-eto-zachem-i-kak-vybrat)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Cтек протоколов TCP/IP

    <p align="center"><img src="./files/network-internet/tcp-ip.png" alt="TCP/IP"/></p>

    -   [Стек TCP/IP](https://ru.wikipedia.org/wiki/TCP/IP)
        > Модель (набор правил), которая описывает способ передачи данных от источника информации к получателю. Будет полезно иметь общее представление, как ваши данные проходят через все уровни протоколов.

    <p align="center"><img src="./files/network-internet/tcp.png" alt="TCP"/></p>

    -   [TCP](https://ru.wikipedia.org/wiki/Transmission_Control_Protocol)
        > Протокол обеспечивающий надежную передачу данных. TCP гарантирует доставку данных и сохранение порядка следования сообщений. Но это сказывается на скорости передачи. Данный протокол используется там, где потеря информации недопустима, например для отправки почты.

    <p align="center"><img src="./files/network-internet/udp.png" alt="UDP"/></p>

    -   [UDP](https://ru.wikipedia.org/wiki/UDP)
        > Простой протокол с быстрой передачей данных. Он не использует механизмов для гарантирования доставки и порядка следования данных. Используется, например в онлайн-играх, где частичная потеря пакетов не критична, но скорость передачи данных имеет гораздо более важное значение. Так же, запросы к DNS-серверам происходят через UDP протокол.
    -   [MAC-адрес](https://ru.wikipedia.org/wiki/MAC-%D0%B0%D0%B4%D1%80%D0%B5%D1%81)
        > Уникальный идентификатор, назначенный сетевому адаптеру какого-либо устройства.

    > -   **[Модель и стек протоколов TCP/IP — YouTube](https://www.youtube.com/watch?v=UZo4ffQ-aAc&list=PLtPJ9lKvJ4oiNMvYbOzCmWy6cRzYAh9B1&index=8&ab_channel=AndreySozykin)**
    > -   **[Протокол TCP — YouTube](https://www.youtube.com/watch?v=CKUOb4htnB4&ab_channel=AndreySozykin)**
    > -   **[Протокол UDP — YouTube](https://www.youtube.com/watch?v=GBrLfZvRrd8&ab_channel=AndreySozykin)**
    > -   **[Всё, что вы хотели знать о МАС адресе — habr.com](https://habr.com/ru/post/483670/)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Проблемы сети

    <p align="center"><img src="./files/network-internet/Problems.gif" alt="Problems"/></p>

    Качество работы сетей, и тем более интернета, далеко от идеала. Это обусловлено сложной и рассредоточенной, по разным устройствам, структурой сети. Поэтому на функционирование сети влияет огромное количеств факторов. Например: стабильность соединения между устройством клиента и его роутером, качество услуг провайдера, мощность и производительность сервера, физическое расстояние между клиентом и сервером и т.д.

    > -   **[Лаги, джиттер и потеря пакетов: откуда берутся проблемы с неткодом и как их решать – habr.com](https://habr.com/ru/company/pixonic/blog/559780/)**
    > -   **[Время ожидания (latency) – MDN (mozilla.org)](https://developer.mozilla.org/ru/docs/Web/Performance/Understanding_latency)**
    > -   **[Как находить проблемы с интернетом и кто виноват ч.1 – habr.com](https://habr.com/ru/post/530324/)**
    > -   **[Как находить проблемы с интернетом и кто виноват ч.2 – habr.com](https://habr.com/ru/post/531082/)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### IPv4 и IPv6

    <p align="center"><img src="./files/network-internet/IPv4-IPv6.png" alt="IPv4-IPv6"/></p>

    -   [IPv4](https://ru.wikipedia.org/wiki/IPv4) и [IPv6](https://ru.wikipedia.org/wiki/IPv6)
        > Cоответственно 4 и 6 версии IP-адреса. IPv4 разработана в 1981 году и ограничивает адресное пространство около 4.3 млрд (2^32) возможными уникальными адресами. Но со временем распределение адресного пространства стало происходить значительно более быстрыми темпами, что вынудило создание новой версии IP-адреса для хранения большего количества адресов. IPv6 способен обеспечить более 300 млн IP-адресов на каждого жителя Земли.

    > -   **[Протоколы IPv4 и IPv6. В чем разница и что лучше?](https://bezopasnik.info/%D0%BF%D1%80%D0%BE%D1%82%D0%BE%D0%BA%D0%BE%D0%BB%D1%8B-ipv4-%D0%B8-ipv6-%D0%B2-%D1%87%D0%B5%D0%BC-%D1%80%D0%B0%D0%B7%D0%BD%D0%B8%D1%86%D0%B0-%D0%B8-%D1%87%D1%82%D0%BE-%D0%BB%D1%83%D1%87%D1%88%D0%B5/)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Трассировка маршрутов

    <p align="center"><img src="./files/network-internet/Traceroute.png" alt="Traceroute"/></p>

    Процедура, позволяющая отследить по каким узлам, с какими IP адресами, передаётся отправленный вами пакет прежде чем он достигнет точки назначения. Трассировка может применяться для выявления связанных с работой компьютерной сети проблем, а также для исследования/анализа сети.

    > -   **[Трассировка сетевого маршрута — hackware.ru](https://hackware.ru/?p=9210#12)**
    > -   **[Traceroute — Википедия](https://ru.wikipedia.org/wiki/Traceroute)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

## Операционные системы

[Операционная система (ОС)](https://ru.wikipedia.org/wiki/%D0%9E%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D0%B0%D1%8F_%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B0) – это комплексная программная система, которая предназначена для эффективного распределения вычислительных ресурсов компьютера. Благодаря операционным системам пользователи могут без всякого труда использовать компьютеры для решения различных задач. То есть людям не приходится иметь дело непосредственно с процессором, оперативной памятью или другими комплектующими ПК.

На данном этапе нет необходимости в детальном изучении устройства и принципов работы ОС. Достаточно лишь общего понимания, как в целом функционирует вся эта система, чтобы для вас это не было каким-то чёрным ящиком.

-   ### Как работают ОС

> **[Что такое операционная система и как она работает – YouTube](https://www.youtube.com/watch?v=hb9CTGSJm88&t) <br>[Что такое операционная система и как она работает? - GitHub](https://github.com/Steindvart/My_study/blob/master/docs/source/OS/articles/what_is_os.rst)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Управление процессами

> **[Процесс – Википедия](<https://ru.wikipedia.org/wiki/%D0%9F%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81_(%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D0%B8%D0%BA%D0%B0)>) <br> [Процессы и потоки](https://learnc.info/c/processes_and_threads.html)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Потоки и параллелизм

> **[Поток выполнения – Википедия](https://ru.wikipedia.org/wiki/%D0%9F%D0%BE%D1%82%D0%BE%D0%BA_%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F) <br> [Параллелизм против многопоточности против асинхронного программирования: разъяснение – habr.com](https://habr.com/ru/post/337528/)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Управление памятью

> **[Управление памятью в ОС](https://bestprogrammer.ru/izuchenie/upravlenie-pamyatyu-v-operatsionnoj-sisteme)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Межпроцессорное взаимодействие

> **[Межпроцессное взаимодействие – Википедия](https://ru.wikipedia.org/wiki/%D0%9C%D0%B5%D0%B6%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%BD%D0%BE%D0%B5_%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D0%B5) <br> [IPC: основы межпроцессного взаимодействия](https://www.rsdn.org/article/baseserv/ipc.xml)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Ввод и вывод (I/O)

> **[Ввод и вывод – Википедия](https://ru.wikipedia.org/wiki/%D0%92%D0%B2%D0%BE%D0%B4-%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4) <br> [Основные методы ввода-вывода (I/O) – tproger.ru](https://tproger.ru/translations/diversity-of-input-output-io/)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Основы POSIX

> **[POSIX – Википедия](https://ru.wikipedia.org/wiki/POSIX) <br> [Что такое POSIX](http://citforum.ru/operating_systems/articles/posix.shtml)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

## Основы Linux

Операционные системы на базе [ядра Linux](https://ru.wikipedia.org/wiki/%D0%AF%D0%B4%D1%80%D0%BE_Linux) это стандарт в мире серверной разработки, поскольку большинство серверов работают именно на таких ОС. Использовать Linux на серверах выгодно, ведь он рапространяется бесплатно.

Существует огромное количество дистрибутивов (сборок с набором предустановленного ПО) Linux на любой вкус и цвет. Одним из самых популярных является [Ubuntu](https://ru.wikipedia.org/wiki/Ubuntu). Именно с него можно начать своё погружение в серверную разработку.

[Установить Ubuntu](https://ubuntu.com/download/desktop) можно на отдельный ПК или ноутбук. Если такой возможности нет, можно воспользоваться специальной программой [Virtual Box](https://www.virtualbox.org/wiki/Downloads), в которой можно [запускать другие ОС](https://lumpics.ru/how-install-ubuntu-on-virtualbox-virtual-machine/) поверх основной. Так же можно запустить [Docker](https://www.docker.com/products/docker-desktop) [контейнер с образом Ubuntu](https://losst.ru/zapusk-kontejnera-docker) (Docker - это отдельная тема, которая рассматривается в этом репозитории).

После этого можно быстро пройти [вводный курс по Linux и Bash](https://younglinux.info/bash/linux).

-   ### Работа с терминалом

    -   [Терминал (или консоль)](https://ru.wikipedia.org/wiki/%D0%98%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81_%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%BD%D0%BE%D0%B9_%D1%81%D1%82%D1%80%D0%BE%D0%BA%D0%B8)
        > Программа-эммулятор, в которой для управления компьютером используются специальные текстовые команды. Как правило на серверах отсутствуют графические оболочки, поэтому вам обязательно понадобятся навыки работы с терминалом.
    -   Основные команды для навигации по файловой системе
        ```bash
        ls # просмотр содержимого директории
        cd <путь> # переход в указанный каталог
        cd .. # переход на уровень выше (в родительский каталог)
        touch <файл> # создание файла
        cat > <файл> # ввод текста в файл из консоли (перезапись)
        cat >> <файл> # ввод текста в конец файла (добавление)
        cat/more/less <файл> # просмотр содержимого файла
        head/tail <файл> # просмотр первых/последних строк файла
        pwd # путь к текущей директории
        mkdir <имя> # создать директорию
        rmdir <имя> # удалить директорию
        cp <файл> <путь> # копировать файл или директорию
        mv <файл> <путь># перемещение или переименование
        rm <файл> # удаление файла или директории
        find <строка># поиск в файловой системе
        du <файл># вывод размера файла или каталога
        ```
    -   Команды для получения справочной информации
        ```bash
        man <название_команды> # позволяет посмотреть руководство по любой команде.
        apropos <слово> # поиск команды с описанием имеющим указанное слово
        man -k <слово> # аналогично команде выше
        whatis <название_команды> # краткое описание команды
        ```
    -   Права суперпользователя
        > Аналог запуска от имени администратора в Windows.
        ```bash
        sudo <команда> # выполняет команду с правами суперпользователя
        ```

    > -   **[Основные linux-команды для новичка – habr.com](https://habr.com/ru/post/501442/)**
    > -   **[44 команды Linux которые вы должны знать – losst.ru](https://losst.ru/42-komandy-linux-kotorye-vy-dolzhny-znat)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Менеджер пакетов

    Встроенный менеджер пакетов [apt (advanced packaging tool)](https://ru.wikipedia.org/wiki/Advanced_Packaging_Tool) позволяет устанавливать/обновлять программные пакеты из сети с помощью терминала.

    -   Базовые команды
        ```bash
        apt install <имя_пакета> # установить пакет
        apt remove <имя_пакета> # удалить пакет, но оставить конфигурацию
        apt purge <имя_пакета> # удалить пакет вместе с конфигурацией
        apt update # обновление информации о новых версиях пакетов
        apt upgrade # обновление пакетов, установленных в системе
        apt list --installed # список установленных в системе пакетов
        apt list --upgradable # список пакетов, которые требуют обновления
        apt search <имя> # поиск пакетов по имени в сети
        apt show <имя_пакета> # информация о пакете
        ```

    > -   **[Как пользоваться apt – losst.ru](https://losst.ru/kak-polzovatsya-apt)**
    > -   **[Использование APT. Команды apt и apt-get – pingvinus.ru](https://pingvinus.ru/note/apt)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Скрипты Bash

    С помощью скриптов (сценариев) можно автоматизировать последовательный ввод любого количества команд. В [Bash](https://ru.wikipedia.org/wiki/Bash#%D0%A1%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D1%8B) можно создавать различные условия (разветвления), циклы, таймеры и т.д. для выполнения всевозможных действий связанных с вводом в консоль.

    > **[Bash-скрипты: начало – habr.com](https://habr.com/ru/company/ruvds/blog/325522/)**
    > **[Шпаргалка оп Bash – quickref.me](https://quickref.me/bash)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Пользователи

    ОС на базе Linux являются многопользовательскими. Это означает, что много людей могут одновременно запускать множество различных приложений одновременно на одном и том же компьютере. Чтобы система Linux смогла «узнать» пользователя, он должен войти в систему, соответсвенно каждый пользователь должен иметь уникальное имя и секретный пароль.

    -   Работа с пользователями
        ```bash
        useradd <имя> [ключи] # создать нового пользователя
        passwd <имя> # установить пароль пользователю
        usermod <имя> [ключи] # редактировать пользователя
        usermod -L <имя> # заблокировать пользователя
        usermod -U <имя> # разблокировать пользователя
        userdel <имя> [ключи] # удалить пользователя
        ```
    -   Работа с группами
        ```bash
        groupadd <группа> [ключи] # создать группу
        groupmod <группа> [опции] # редактировать группу
        groupdel <группа> [опции] # удалить группу
        usermod -a -G <группы(через запятую)> <пользователь> # добивить пользователя в группы
        gpasswd --delete <пользователь> <группы(через запятую)> # удалить пользователя из групп
        ```
    -   Системные файлы
        ```bash
        /etc/passwd # файл паролей, содержащий основную информацию о пользователях
        /etc/shadow # файл теневых шифрованных паролей, содержащий зашифрованные пароли
        /etc/group # файл групп, содержащий основную информацию о группах
        /etc/gshadow # файл теневых групп, содержащий шифрованные пароли групп
        ```

    > -   **[Пользователи в Linux – добавление, изменение, удаление](https://host-consult.ru/polzovateli-v-linux/)**
    > -   **[Группы и пользователи в Linux](https://sysadminium.ru/groups_and_users_in_linux/)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Права доступа

    <p align="center"><img src="./files/linux/chmod.png" alt="chmod"/></p>

    Так как под одной ОС могут работать несколько разных пользователи, то соответственно у каждого такого пользователя будет своё личное файловое пространство. Отсюда вытекает, что у любого файла в Linux должны быть специальные атрибуты – права на доступ. Эти атрибуты должны сообщать, кто имеет право работать c тем или иным файлом.

    > -   **[Права доступа в Linux – younglinux.info](https://younglinux.info/bash/rwx)**
    > -   **[Управление доступом в Linux](https://zinvapel.github.io/it/tools/2018/01/10/linux-users/)**
    > -   **[Команда chmod – изменение прав доступа – younglinux.info](https://younglinux.info/bash/chmod)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Работа с процессами

    Процессы в Linux можно описать как контейнеры, в которых хранится вся информация о состоянии выполняемой программы. Если программа работает хорошо, то все нормально, но если она зависла и вам нужно восстановить её работу, тогда вам понадобиться навыки работы по управлению процессами.

    -   Базовые команды
        ```bash
        ps # вывести 'снимок' процессов всех пользователей
        top # диспетчер задач в реальном времени
        <команда> & # запуск процесса в фоновом режиме, то есть не занимая консоль
        jobs # список запущенных в фоновом режиме процессов
        fg <номер> # вернуть процесс обратно в активный режим по его номеру
        bg <номер> # запуск остановленного процесса в фоновый режим
        kill <id процесса> # завершить процесс по id
        killall <программа> # завершить все процессы связанные с одной программой
        ```

    > -   **[Работа с процессами в Linux – YouTube](https://www.youtube.com/watch?v=Y4W_rJStNSA)**
    > -   **[Шпаргалка по работе процессами в Lunux – dmosk.ru](https://www.dmosk.ru/miniinstruktions.php?mini=processes-linux)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Работа с SSH

    -   [Служба SSH](https://ru.wikipedia.org/wiki/SSH)
        > Позволяет получить удаленный доступ к терминалу другого компьютера. В случае с персональным компьютером, это может понадобиться для срочного решения какой-либо проблемы, а в случае с сервером это вообще очень распространенная практика.
    -   Базовые комнады
        ```bash
        apt install openssh-server # установка SSH (хотя он почти везде идёт из коробки)
        service ssh start # запуск SSH
        service ssh stop # остановка SSH
        ssh -p <Порт> user@remotehost # подключенние к удаленному ПК через SSH
        ssh-keygen -t rsa # генерация RSA-ключа для беспарольного входа
        ssh-copy-id -i ~/.ssh/id_rsa user@remotehost # копирования ключа на удаленную машину
        ```

    > -   **[Как пользоваться SSH – losst.ru](https://losst.ru/kak-polzovatsya-ssh)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Планировщик задач

    <p align="center"><img src="./files/linux/cron.png" alt="cron"/></p>

    Благодаря планировщикам можно гибко управлять отложенным запуском команд и скриптов. В Linux есть встроенный планировщик [cron](https://ru.wikipedia.org/wiki/Cron), с помощью которого можно легко выполнять необходимые действия через определенные интервалы времени.

    > -   **[Использование Cron для автоматизации задач – Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-use-cron-to-automate-tasks-ubuntu-1804-ru)**
    > -   **[Crontab: запуск задач по расписанию – YouTube](https://youtu.be/52-eyCp56ew)**
    > -   **[Удобный онлайн-редактор для crontab](https://crontab.guru/)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Системные логи

    -   [Файлы журнала (логи)](https://ru.wikipedia.org/wiki/%D0%A4%D0%B0%D0%B9%D0%BB_%D0%B6%D1%83%D1%80%D0%BD%D0%B0%D0%BB%D0%B0)
        > Cпециальные текстовые файлы, в которые заносится вся информация о работе сервера или компьютера, о действиях программы или пользователя. Поэтому они особенно полезны при возникновении багов и ошибок в работе программы или сервера. Рекомендуется периодически просматривать логи, даже если ничего подозрительного не происходит.

    > -   **[Как посмотреть логи в Linux – losst.ru](https://losst.ru/kak-posmotret-logi-v-linux)**
    > -   **[Лог файлы Linux по порядку – habr.com](https://habr.com/ru/post/332502/)**
    > -   **[Туториал по системным логам Linux](https://proglib.io/p/pomedlennee-ya-zapisyvayu-tutorial-po-sistemnym-logam-linux-2020-07-09)**

<div align="right"><a href="#top">Содержание ⬆️</a></div>

-   ### Проблемы Linux

<div align="right"><a href="#top">Содержание ⬆️</a></div>

## Общие знания

-   ### Системы счисления

-   ### Структуры данных

    -   #### Хэш-таблицы

    -   #### Очередь и стек

    -   #### Связанные списки

    -   #### Двусвязные списки

-   ### Форматы хранения данных

    -   #### Текстовые

    JSON, YAML, XML

    -   #### Бинарные

    Message Pack, BSON, ProtoBuf

-   ### Криптография

    -   #### Хэши и хеш-функции

    -   #### Цифровые подписи

    -   #### Соль для подписей

    -   #### Коллизия хэшей

## Язык программирования

На этом этапе Вам предстоит выбрать для изучения один из языков программирования. В открытом доступе полно информации по различным языкам, поэтому с обучением у Вас не должно возникнуть проблем.

Многие бояться, что могут выбрать плохой или невостребованный язык программирования. Из-за чего начинают искать много ненужной информации по таким вопросам: _"Какой язык лучше?"_, _"Какой самый популярный?"_ и т.д. Это приводит к перепрыгиванию с одного языка на другой. Этого делать не нужно, поскольку **не важно какой язык вы выберете в начале своего пути**. Все языки, плюс минус, основываются на одинаковых принципах. Изучив досконально один из языков вам не составит труда использовать новый, потратив лишь немного времени на изучение синтаксиса и некоторых специфических особенностей. Примите к сведению, что язык программирования - это всего лишь инструмент. Изобилие языков обосновано тем, что каждый язык программирования, как правило, создаётся для решения определённых задач и в чём-то может уступать остальным. Поэтому в будущем, по мере вашего роста, вам всё ровно придётся столкнуться с использованием разных языков.

Тем не менее, ниже приведен список конкретных языков, которые [лично по моему мнению](https://github.com/cheatsnake) хорошо подходят для backend-разработки.

[Python](https://ru.wikipedia.org/wiki/Python) - очень популярный и широко используемый. Лёгкий в изучении, благодаря простому синтаксису.

[JavaScript](https://ru.wikipedia.org/wiki/JavaScript) - не менее популярный и практический единственный язык для полноценной Web-разработки. Благодаря платформе [Node.js](https://nodejs.org) последнее несколько лет набирает популярность и в области backend-разработки.

[Go](https://ru.wikipedia.org/wiki/Go) - язык созданный внутри компании Google. Создавался специально для серверной разработки. Минималистичный, но в то же время обладающий очень богатой стандартной библиотекой.

-   ### Базовые знания

    -   #### Примитивные типы данных

    -   #### Функции

    -   #### Набор, массив, хеш-таблица, кортеж

    -   #### Объекты/классы/структуры, прототипы/интерфейсы/миксины

    -   #### Ссылки, указатели

    -   #### Область видимости переменных

    -   #### Сборщик мусора

    -   #### Преобразование типов

    -   #### Слабая/сильная типизация в коде

    -   #### Битовые операции

    -   #### Обработка ошибок

-   ### Распараллеливание

    -   #### Процессы

    -   #### Потоки

    -   #### КоРутины

    -   #### Проблемы распараллеливания

    -   #### Атомарные операции

    -   #### Блокировки

-   ### Пакетный менеджер

-   ### Отладчик

-   ### Запуск HTTP-сервера

-   ### Кэширование

-   ### Шаблонизация

-   ### Ввод / Вывод (IO)

## Протокол HTTP

-   ### Формат протокола

-   ### Методы HTTP-запросов

-   ### Коды ответов

-   ### Заголовки

-   ### Cookie

-   ### CORS

-   ### CSP

-   ### Безопасность (HTTPS)

-   ### Различия HTTP 1.0 и HTTP 1.1

-   ### HTTP 2

-   ### HTTP 3

-   ### Откладка сети в Chrome Dev Tools

-   ### Работа с HTTP через терминал

-   ### WebSockets

-   ### API форматы

-   ### Web сервера

    -   #### NGNX

    -   #### Apache httpd

## Базовое ПО

-   ### Система контроля версий Git

-   ### Контейнеризация и Docker

-   ### Postman / Insomnia

## Базы данных

-   ### Реляционные базы данных

-   ### Документоориентированные базы данных

-   ### Redis

-   ### Проблемы баз данных

## Дополнительные материалы и источники

-   [Backend Developer Roadmap: Learn to become a modern backend developer](https://roadmap.sh/backend)
-   [bzick/oh-my-backend: Backend Roadmap (from Junior to Senior)](https://github.com/bzick/oh-my-backend)
-   [zhashkevych/awesome-backend: 🚀 A curated and opinionated list of resources (English & Russian) for Backend developers](https://github.com/zhashkevych/awesome-backend)
-   [УЧЕБНЫЙ КУРС: Компьютерные сети](https://www.asozykin.ru/courses/networks_online)

<div align="center">Made with &#9829;</div>
<div align="center"><a href="https://github.com/cheatsnake/backend-cheats/blob/master/LICENSE">LICENSE</a> 2022.</div>
