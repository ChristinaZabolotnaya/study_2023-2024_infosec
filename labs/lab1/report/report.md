---
## Front matter
title: "Stepik ПО ОСНОВАМ ИНФОРМАЦИОННОЙ БЕЗОПАСНОСТИ"
subtitle: "Курс Stepik - Основы кибербезопасности"
author: "Заболотная Кристина Александровна"

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
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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

# 1.1 О курсе

# 2.  Безопасность в сети

## 2.1 Как работает интернет: базовые сетевые протоколы

### Протокол прикладного уровня - HTTPS.
Протокол HTTP(S) является примером протокола прикладного уровня, по которому передаются веб-страницы. [@tanenbaum_book_modern-os_ru]

![HTTPS](image/1.png){#fig:001 width=90%}

### Уровень работы протокола TCP – Транспортный.
На транспортном уровне существует два примера протокола: первый — это TCP, в честь которого названа модель. Этот протокол, в отличие от второго примера – UDP, обеспечивает надежную передачу пакетов.

![Транспортный](image/2.png){#fig:002 width=90%}

### Все корректные адреса IPv4 - 90.11.90.22, 25.198.0.15.
Например, адрес IPv4 может выглядеть вот так: 192.168.1.4. Первые три числа — это номер сети.

![90.11.90.22, 25.198.0.15](image/3.png){#fig:003 width=90%}

### DNS сервер - сопоставляет IP адреса доменным именам.
Доменное имя — это как раз-таки то, что мы называем ссылкой - yandex.ru, google.com, mail.ru и так далее. И основная задача этого DNS-сервера — это сопоставить название, то есть доменное имя, с корректным 
IP-адресом, с тем, где лежит этот сервер, этот сайт.

![IP](image/4.png){#fig:004 width=90%}

### Корректная последовательность протоколов в модели TCP/IP - прикладной -- транспортный -- сетевой – канальный.
Документами, определяющими сертификацию модели, являются RFC 1122 и RFC1123. Эти стандарты описывают четыре уровня абстракции модели TCP/IP: прикладной, транспортный, межсетевой и канальный.

![прикладной -- транспортный -- сетевой – канальный](image/5.png){#fig:005 width=90%}

### Протокол http предполагает - передачу данных между клиентом и сервером в открытом виде.
Принцип взаимодействия на основе протокола HTTP основан на схеме "запрос-ответ" и предполагает следующую последовательность действий: клиент формирует сообщение-запрос и передает серверу; сервер получает сообщение, анализирует и обрабатывает запрос, формирует сообщение-ответ и направляет его клиенту.

![передачу данных между клиентом и сервером в открытом виде](image/6.png){#fig:006 width=90%}

### Протокол https состоит из - двух фаз: рукопожатия и передачи данных.
Клиент устанавливает TCP соединения (или другое соединение, если не используется TCP транспорт) и клиент отправляет запрос и ждёт ответа (сервер обрабатывает запрос и посылает ответ, в котором содержится код статуса и соответствующие данные). 

![двух фаз: рукопожатия и передачи данных](image/7.png){#fig:007 width=90%}

### Версия протокола TLS определяется - и клиентом, и сервером в процессе “переговоров”.
 Протокол, используемый для данного подключения, зависит от возможностей соответствующих компонентов как на стороне клиента, так и на стороне сервера. 
 
![и клиентом, и сервером в процессе “переговоров”](image/8.png){#fig:008 width=90%}

### В фазе “рукопожатия” протокола TLS не предусмотрено - шифрование данных.
В ходе TLS-рукопожатия клиент и сервер вместе: указывают, какую версию TLS (TLS 1.0, 1.2, 1.3 и т. д.) они будут использовать. Решают, какие наборы шифров (см. ниже) они будут использовать. Проверяют подлинность сервера с помощью открытого ключа сервера и цифровой подписи центра сертификации SSL. Генерируют сеансовые ключи, чтобы использовать симметричное шифрование после завершения рукопожатия.

![шифрование данных](image/9.png){#fig:009 width=90%}

## 2.2 Персонализация сети

### Куки хранят - идентификатор пользователя, id сессии.
Куки, как правило, хранят в себе список параметров и их значений. Этими параметрами могут быть id пользователя, id сессии, иногда описан тип браузера и время запросов, и некоторые действия пользователей.

![идентификатор пользователя, id сессии](image/10.png){#fig:010 width=90%}

### Куки не используются для - улучшения надежности соединения.
Cookies используются при навигации на сайте и удаляются при закрытии окна браузера. Используются при аутентификации, сборе статистики посещаемости сайта, персонализации веб-страниц, отслеживания информации 
о пользователе.

![улучшения надежности соединения](image/11.png){#fig:011 width=90%}

### Куки генерируются – сервером.
Сервер кодирует настройки в cookie и отправляет cookie обратно в браузер. Таким образом, каждый раз, когда пользователь получает доступ к странице на веб-сайте, сервер может персонализировать страницу в соответствии с предпочтениями пользователя.

![сервером](image/12.png){#fig:012 width=90%}

### Сессионные куки хранятся в браузере - Да, на время пользования веб-сайтом. 
Сессионные cookies являются временными файлами, которые сохраняются в браузере пользователя только до тех пор, пока он находится на веб-сайте.

![Да, на время пользования веб-сайтом](image/13.png){#fig:013 width=90%}

## 2.3 Браузер TOR. Анонимизация.

### Сколько промежуточных узлов в луковой сети TOR – 3.
Для каждого запроса случайно выбирается маршрут через один из трех узлов, а каждый следующий узел шифрует предыдущий.

![3](image/14.png){#fig:014 width=90%}

### IP-адрес получателя известен – отправителю и выходному узлу. 
Когда отправитель отправляет данные через интернет, он указывает IP-адрес получателя в заголовке пакета данных. Этот IP-адрес известен отправителю, так как он сам его указал, и выходному узлу, который используется для маршрутизации пакетов к конечному получателю. Таким образом, IP-адрес получателя является необходимой информацией для передачи данных в сети.

![отправителю и выходному узлу](image/15.png){#fig:015 width=90%}

### Отправитель генерирует общий секретный ключ - с охранным, промежуточным и выходном узлом.
Когда отправитель генерирует общий секретный ключ для связи с другим узлом (охранной, промежуточной или выходной точкой), он использует различные криптографические методы для создания этого ключа. Общий секретный ключ позволяет обеспечить конфиденциальность и целостность передаваемых данных между узлами. После генерации общего секретного ключа отправитель и получатель могут использовать его для шифрования и расшифрования данных, а также для проверки целостности сообщений. Это позволяет им обмениваться информацией безопасным образом, чтобы третьи лица не могли перехватить или изменить передаваемые данные.

![с охранным, промежуточным и выходном узлом](image/16.png){#fig:016 width=90%}

### Должен ли получатель использовать браузер Tor для успешного получения пакетов – нет. 
Получатель не обязан использовать браузер Tor или другой браузер, основанный на луковой маршрутизации, для успешного получения пакетов с общим секретным ключом от отправителя. Луковая маршрутизация, такая как та, что используется в сети Tor, предназначена для обеспечения анонимности и защиты конфиденциальности пользователей в интернете путем маршрутизации их трафика через несколько узлов.

![нет](image/17.png){#fig:017 width=90%}

## 2.4 Беспроводные сети Wi-fi

### Wi-Fi – это - технология беспроводной локальной сети, работающая в соответствии со стандартом IEEE 802.11.
WiFi - это технология беспроводной локальной сети, она основана на стандарте IEEE 802.11. IEEE – это организация, которая описывает вообще любые стандарты того, как работает интернет.

![IEEE 802.11](image/18.png){#fig:018 width=90%}

### Уровень работы протокола WiFi – канальный. 
WiFi работает на самом нижнем канальном уровне, на том же уровне, где работает протокол Ethernet (это протокол, обеспечивающий продвижение данных по проводу). И в этом нет ничего удивительного, поскольку по своей сути технология WiFi очень похожа на технологию Ethernet, только передает данные не по кабелю, а по радиосигналу. 

![канальный](image/19.png){#fig:019 width=90%}

### Небезопасный метод обеспечения шифрования и аутентификации в сети Wi-Fi – WEP.
Самый ранний и на сегодняшний день небезопасный метод шифрования данных WiFi называется WEP. Он устарел и уже категорически не рекомендуется к использованию. Он устарел, в частности, потому, что использовал малую длину ключа: так, например, он использовал длину ключа в 40 бит, это довольно мало на сегодняшний день, он может быть легко взломан. 

![WEP](image/20.png){#fig:020 width=90%}

### Данные между хостом сети (компьютером или смартфоном) и роутером - передаются в зашифрованном виде после аутентификации устройств.
Для обеспечения безопасности и конфиденциальности данных, передаваемых между хостом и роутером, обычно используются различные методы шифрования и аутентификации. Например, когда устройство подключается к защищенной беспроводной сети Wi-Fi, происходит процесс аутентификации, где устройство подтверждает свою легитимность перед роутером. После успешной аутентификации устанавливается защищенное соединение с помощью протокола шифрования, такого как WPA2 (Wi-Fi Protected Access 2), который обеспечивает шифрование данных, передаваемых между устройством и роутером.

![передаются в зашифрованном виде после аутентификации устройств](image/21.png){#fig:021 width=90%}

### Для домашней сети для аутентификации обычно используется метод - WPA2 Personal. 
WPA2 Personal является одним из наиболее распространенных методов шифрования и аутентификации для защиты беспроводных сетей. Когда вы настраиваете свою домашнюю Wi-Fi сеть, вы обычно устанавливаете пароль (проходную фразу) для доступа к сети. Этот пароль используется для аутентификации устройств, которые пытаются подключиться к вашей сети. Когда устройство пытается подключиться к вашей защищенной сети Wi-Fi, оно должно предоставить правильный пароль для аутентификации через протокол WPA2 Personal.

![WPA2 Personal](image/22.png){#fig:022 width=90%}

# 3. Защита ПК/телефона

## 3.1 Шифрование диска

### Можно ли зашифровать загрузочный сектор диска – да. 
Можно шифровать и загрузочный сектор диска.

![да](image/23.png){#fig:023 width=90%}

### Шифрование диска основано на - симметричном шифровании. 
Шифрование больших объемов данных, например, жесткого диска или сегмента жесткого диска или какой-то большой флешки, осуществляется с помощью симметричного шифрования, как правило, алгоритма AES.

![симметричном шифровании](image/24.png){#fig:024 width=90%}

### С помощью каких программ можно зашифровать жесткий диск – VeraCrypt, BitLocker.
Во всех популярных операционных системах есть встроенные утилиты, которые позволяют шифровать жесткий диск: для Windows этo Bitlocker, в Linux – LUKS, в MacOS – это FileVault. Кроме того, есть и сторонние опенсорсные (open source) программы, то есть бесплатные: это Veracrypt, PGPDisk, которые вы можете установить себе и использовать их для шифрования ваших жестких дисков, загрузочных секторов или флешек. 

![VeraCrypt, BitLocker](image/25.png){#fig:025 width=90%}

## 3.2 Пароли

### Какие пароли можно отнести с стойким - UQr9@j4!S$.
Наши пароли - это банальный перебор всевозможных паролей, если мы знаем, что, например, пароль состоит из цифр и букв алфавита и каких-то еще символов, мы знаем в принципе весь алфавит, мощность этого 
алфавита, если мы еще, допустим, знаем длину пароля, то мы можем точно посчитать, каков размер множества всех паролей.

![UQr9@j4!S$](image/26.png){#fig:026 width=90%}

### Где безопасно хранить пароли - в менеджерах паролей.
Нужно использовать длинные пароли с максимально большим алфавитом, хранить их стоит в менеджерах паролей, пароли нужно менять достаточно регулярно, особенно к таким критическим сервисам, как почта.

![в менеджерах паролей](image/27.png){#fig:027 width=90%}

### Зачем нужна капча - для защиты от автоматизированных атак, направленных на получение несанкционированного доступа.
Капча — это аббревиатура с английского; это тест для определения, является ли пользователь, который общается с веб-сервисом, человеком или компьютером, ботом, которой пытается просто-напросто перебрать все пароли. В сети часто используется такая защита, как капча.

![для защиты от автоматизированных атак, направленных на получение несанкционированного доступа](image/28.png){#fig:028 width=90%}

### Для чего применяется хэширование паролей - для того, чтобы не хранить пароли на сервере в открытом виде.
Хэширование паролей - это процесс преобразования введенного пользователем пароля в некоторую строку фиксированной длины (хэш), которая затем сохраняется на сервере. Главная цель хэширования паролей - это обеспечение безопасности хранения пользовательских паролей. 

![для того, чтобы не хранить пароли на сервере в открытом виде](image/29.png){#fig:029 width=90%}

### Поможет ли соль для улучшения стойкости паролей к атаке перебором, если злоумышленник получил доступ к серверу – нет.
Соль используется для того, чтобы увеличить стойкость пароля для пользователей, которые сами не догадались о стойкости своих паролей. 

![нет](image/30.png){#fig:030 width=90%}

### Какие меры защищают от утечек данных атакой перебором – разные пароли на всех сайтах, капча, сложные пароли, периодическая смена паролей. 

![разные пароли на всех сайтах, капча, сложные пароли, периодическая смена паролей](image/31.png){#fig:031 width=90%}

## 3.3 Фишинг

### Какие из следующих ссылок являются фишинговыми – Сбербанк онлайн, аккаунт Яндекс. 

![Сбербанк онлайн, аккаунт Яндекс](image/32.png){#fig:032 width=90%}

### Может ли фишинговый имейл прийти от знакомого адреса – да. 
Спуфинг – это глобальный термин атак, есть IP spoofing - это подмена IP-адреса, есть email spoofing - подмена адреса отправителя. Суть состоит в том, что мы получаем фишинговое письмо от якобы знакомого нам человека, а на самом деле отправлено оно было не им.

![да](image/33.png){#fig:033 width=90%}

## 3.4 Вирусы. Примеры

### Email Спуфинг – это подмена адреса отправителя в имейлах. 
Спуфинг – это глобальный термин атак, есть IP spoofing - это подмена IP-адреса, есть email spoofing - подмена адреса отправителя.

![это подмена адреса отправителя в имейлах](image/34.png){#fig:034 width=90%}

### Вирус-троян - маскируется под легитимную программу.
Троян - это вирус, который проникает в систему под видом какого-то легитимного программного обеспечения, это аллюзия к троянскому коню. Этот вирус также распространялся по почте с вполне себе невинным письмом с темой “Re: Details” (re от слова reply) или подобным ему. Само письмо содержало примечательный текст “See the attached file for details” («Просмотри вложение для подробной информации»). 

![маскируется под легитимную программу](image/35.png){#fig:035 width=90%}

## 3.5 Безопасность мессенджеров

### На каком этапе формируется ключ шифрования в протоколе мессенджеров Signal - при генерации первого сообщения стороной-отправителем. 
Протокол мессенджера Signal использует протокол двойного ratchet для шифрования сообщений, который обеспечивает прямое и обратное шифрование сообщений между отправителем и получателем. Ключи шифрования формируются на различных этапах в процессе обмена сообщениями.

![при генерации первого сообщения стороной-отправителем](image/36.png){#fig:036 width=90%}

### Суть сквозного шифрования состоит в том, что - сообщения передаются по узлам связи (серверам) в зашифрованном виде. 
Сквозное шифрование - это парадигма большого числа безопасных коммуникаций; сквозное шифрование - по-английски E2E или End-to-End encryption.

![сообщения передаются по узлам связи (серверам) в зашифрованном виде](image/37.png){#fig:037 width=90%}

# 4. Криптография на практике

## 4.1 Введение в криптографию

### В асимметричных криптографических примитивах - обе стороны имеют пару ключей.
В асимметричной криптографии (её еще называют криптографией с открытым ключом) у каждой из сторон есть пара ключей: открытый ключ и секретный ключ. 

![обе стороны имеют пару ключей](image/38.png){#fig:038 width=90%}

### Криптографическая хэш-функция - дает на выходе фиксированное число бит независимо от объема входных данных, эффективно вычисляется, стойкая к коллизиям.
Криптографическая хэш-функция - это функция, которая принимает входные данные любого размера и преобразует их в фиксированный набор битов, называемый хэшем. Она обладает свойствами такими как эффективность в вычислениях, необратимость (невозможность восстановления исходных данных из хэша), устойчивость к коллизиям (когда два разных входных значения дают одинаковый хэш) и многими другими. Криптографические хэш-функции широко используются в криптографических системах для обеспечения безопасности данных, а также в цифровой подписи, проверке целостности данных и хранения паролей.

![дает на выходе фиксированное число бит независимо от объема входных данных, эффективно вычисляется, стойкая к коллизиям](image/39.png){#fig:039 width=90%}

### К алгоритмам цифровой подписи относятся – RSA, ECDSA, ГОСТ Р 34.10-2012.
К примерам цифровой подписи относятся интернет-сертификаты, подпись RSA, американский стандарт ECDSA и отечественный стандарт ГОСТ стандарт P 34.20.2012. 

![RSA, ECDSA, ГОСТ Р 34.10-2012](image/40.png){#fig:040 width=90%}

### Код аутентификации сообщения относится к - симметричным примитивам. 
Как правило, код аутентификации сообщения строится с помощью хэш-функции или симметричного шифрования. 

![симметричным примитивам](image/41.png){#fig:041 width=90%}

### Обмен ключам Диффи-Хэллмана – это асимметричный примитив генерации общего секретного ключа. 
Самым популярным примером протокола обмена ключами является протокол Диффи-Хэллмана, как раз он, либо его модификации используются в современных мессенджерах и в протоколе TLS для того, чтобы мы смогли сгенерировать общий секретный ключ и дальше шифровать наши данные с помощью симметричного алгоритма, то есть с помощью ключа skAB. Если реализовать генерацию общего ключа так, как она описана у Диффи-Хэллмана, мы получим довольно слабый протокол, нестойкий к активным злоумышленникам. Сделать этот протокол стойким к активным злоумышленникам помогает цифровая подпись. 

![это асимметричный примитив генерации общего секретного ключа](image/42.png){#fig:042 width=90%}

## 4.2. Цифровая подпись

### Протокол электронной цифровой подписи относится к - протоколам с публичным (или открытым) ключом.
Протокол электронной цифровой подписи (ЭЦП) относится к протоколам с публичным ключом, также известным как открытым ключом, потому что он использует два ключа - приватный и публичный. Публичный ключ используется для проверки подписи, в то время как приватный ключ используется для создания подписи. При использовании ЭЦП отправитель использует свой приватный ключ для создания уникальной цифровой подписи, которая затем отправляется вместе с документом. Получатель может затем использовать публичный ключ отправителя для проверки подлинности подписи и целостности документа. Таким образом, протокол ЭЦП обеспечивает возможность проверки подлинности документов и их авторства в сети с публичным доступом к ключам.

![протоколам с публичным (или открытым) ключом](image/43.png){#fig:043 width=90%}

### Алгоритм верификации электронной цифровой подписи требует на вход - подпись, открытый ключ, сообщение. 
Если говорить более формально о том, что такое электронно-цифровая подпись, то это криптографический примитив, который состоит из трех эффективных алгоритмов. Эффективный алгоритм означает, что мы можем быстро его запустить на не сильно мощной машине. Первый алгоритм занимается генерацией ключей, он генерирует публичный ключ и секретный ключ. Публичный ключ мы держим в открытом доступе, секретный ключ – у себя, никому не показываем. Секретный ключ еще называется подписывающим ключом, а открытый – проверяющим или ключом верификации. Второй алгоритм – это генерация подписи, которая берет на вход сообщение и секретный ключ и выдает нам подпись. И третий – это верификация подписи, которая берёт на вход подпись, сообщение и открытый ключ и выдает нам либо тот факт, что подпись верна, либо тот факт, что подпись неверна. 

![подпись, открытый ключ, сообщение](image/44.png){#fig:044 width=90%}

### Электронная цифровая подпись не обеспечивает – конфиденциальность.
Электронная цифровая подпись (ЭЦП) не обеспечивает конфиденциальность данных. Её основная цель - подтверждение подлинности и целостности данных, то есть их авторства и неприкосновенности. ЭЦП позволяет убедиться, что документ или сообщение были созданы конкретным отправителем и не были изменены после подписания. Для обеспечения конфиденциальности данных, таких как защита от несанкционированного доступа или прослушивания, обычно используются другие методы, такие как алгоритмы шифрования. Эти методы позволяют шифровать данные таким образом, что только авторизованные пользователи могут расшифровать их.

![конфиденциальность](image/45.png){#fig:045 width=90%}

### Какой тип сертификата электронной подписи понадобится для отправки налоговой отчетности в ФНС - усиленная квалифицированная.
Усиленная квалифицированная электронная подпись (УКЭП) – это специальный тип сертификата электронной подписи, который обладает увеличенным уровнем достоверности и законной силой. Этот тип ЭП используется для подписания важных и юридически значимых документов, таких как налоговая отчетность, передаваемая в Федеральную налоговую службу (ФНС). Чтобы получить усиленную квалифицированную электронную подпись, необходимо обратиться к аккредитованному удостоверяющему центру (УЦ), который проведет проверку личности подписанта и выдаст соответствующий сертификат. Такие сертификаты имеют особые требования к процедурам проверки личности и могут быть использованы для юридически значимых документов.

![усиленная квалифицированная](image/46.png){#fig:046 width=90%}

### В какой организации вы можете получить квалифицированный сертификат ключа проверки электронной подписи - в удостоверяющем (сертификационном) центре.
Квалифицированный сертификат ключа проверки электронной подписи (КЭП) можно получить в удостоверяющем центре (УЦ), который является специализированной организацией, уполномоченной на выдачу сертификатов ключей электронных подписей. УЦ проводит процедуры проверки подлинности идентификационных данных заявителя, выпускает и распространяет сертификаты ключей электронных подписей, управляет их отзывом при необходимости, а также обеспечивает безопасность и надежность процесса выдачи и использования сертификатов. Получение квалифицированного сертификата ключа проверки электронной подписи на УЦ включает в себя предъявление документов, подтверждающих личность, прохождение процедур авторизации и подтверждения личности, и подписание необходимых соглашений. УЦ должен быть аккредитован уполномоченным государственным органом и соответствовать установленным законодательством требованиям по выдаче квалифицированных сертификатов ключей электронных подписей.

![в удостоверяющем (сертификационном) центре](image/47.png){#fig:047 width=90%}

## 4.3 Электронные платежи

### Выберите из списка все платежные системы – MasterCard, МИР.

![MasterCard, МИР](image/48.png){#fig:048 width=90%}

### Примером многофакторной аутентификации является - комбинация код в sms сообщении + отпечаток пальца, комбинация проверка пароля + код в sms сообщении. 
Многофакторная аутентификация - это процесс подтверждения личности пользователя с использованием двух или более различных методов аутентификации. Примеры, которые вы привели, отлично иллюстрируют это: 1. Комбинация кода из SMS-сообщения и отпечатка пальца: В этом случае пользователю необходимо предоставить два разных типа подтверждения - что-то, что он знает (код из SMS) и что-то, что он имеет (отпечаток пальца). Это повышает безопасность, так как злоумышленнику будет сложнее обойти оба уровня защиты. 2. Проверка пароля и кода из SMS-сообщения: Здесь также сочетаются два различных метода - что-то, что пользователь знает (пароль) и что-то, что он получает на внешнем устройстве (код из SMS). Это создает двойную проверку личности и уменьшает риск несанкционированного доступа.

![комбинация код в sms сообщении + отпечаток пальца, комбинация проверка пароля + код в sms сообщении](image/49.png){#fig:049 width=90%}

### При онлайн платежах сегодня используется - многофакторная аутентификация покупателя перед банком-эмитентом.
В сфере онлайн платежей сегодня все более широко внедряется многофакторная аутентификация покупателя перед банком-эмитентом. Это означает, что при совершении онлайн транзакций покупателю требуется предоставить несколько различных методов аутентификации для подтверждения своей личности перед банком, который выпускает его платежную карту. Например, при совершении онлайн платежа покупателю может потребоваться ввести свой пароль или PIN-код (что-то, что он знает), а затем получить одноразовый код подтверждения на свой мобильный телефон (что-то, что он имеет). Такая комбинация факторов делает процесс аутентификации более надежным и защищает от мошенничества, поскольку злоумышленнику будет гораздо сложнее обойти оба уровня защиты. Многофакторная аутентификация позволяет банкам повысить безопасность онлайн платежей, защитить клиентов от несанкционированных транзакций и уменьшить риски финансовых мошенничеств.

![многофакторная аутентификация покупателя перед банком-эмитентом](image/50.png){#fig:050 width=90%}

## 4.4 Блокчейн

### Какое свойство криптографической хэш-функции используется в доказательстве работы - сложность нахождения прообраза.
Криптографическая хэш-функция обладает свойством сложности нахождения прообраза, что означает, что для заданного значения хэш-суммы сложно найти исходное сообщение, которое бы привело к данной хэш-сумме. Это свойство является важным для обеспечения безопасности данных и целостности информации. При использовании криптографической хэш-функции, например, при хэшировании паролей или цифровой подписи, важно, чтобы невозможно было найти исходное сообщение, зная только его хэш-сумму. То есть, даже при наличии хэш-суммы злоумышленнику будет крайне сложно или практически невозможно восстановить исходное сообщение. Это свойство обеспечивает уровень безопасности, так как даже при доступе к хэш-сумме злоумышленнику будет трудно восстановить исходное сообщение без знания алгоритма хэширования и без изначальных данных. Таким образом, сложность нахождения прообраза является важным криптографическим свойством, обеспечивающим надежность и безопасность при работе с хэш-функциями.

![сложность нахождения прообраза](image/51.png){#fig:051 width=90%}

### Консенсус в некоторых системах блокчейн обладает свойствами – постоянства, открытость, живучесть, консенсус. 
В основе любого блокчейна, в частности биткоина, лежит консенсус – соглашение, в терминах криптовалют консенсус - это некая публичная структура данных или ledger (переводится с английского как «бухгалтерская книга»), где просто содержится история всех переводов, хранится список того, кто что кому заплатил, в какое время. Почему консенсус? Потому что эта публичная структура, и бухгалтерский учет должен обеспечивать четыре основных свойства. Первое - это постоянство, то есть когда-либо добавленНые данные не должны быть удалены из этой структуры. Второе - это сам консенсус, то есть все участники видят одни и те же данные и соглашаются с одним и теми же данными, исключением могут быть последние пары блоков, то есть последние изменения в этом блокчейне, в этой публичной структуре данных. Третье - это живучесть, это означает, что мы можем добавлять новые транзакции, когда хотим, мы можем осуществлять платежи, когда хотим. И последнее четвертое свойство - это открытость, то есть любой человек может быть участником блокчейна. Это справедливо не для всех блокчейнов, для биткоина это справедливо. 

![постоянства, открытость, живучесть, консенсус](image/52.png){#fig:052 width=90%}

### Секретные ключи какого криптографического примитива хранят участники блокчейна - цифровая подпись. 
Участники блокчейна хранят секретные ключи для цифровой подписи. Цифровая подпись - это криптографический примитив, который позволяет участнику блокчейна подтверждать свою личность и подписывать транзакции с использованием своего секретного ключа. При создании цифровой подписи участник использует свой закрытый ключ для шифрования информации о транзакции, и другие участники могут проверить подлинность подписи, используя открытый ключ этого участника. Таким образом, секретный ключ для цифровой подписи является важным элементом для обеспечения безопасности и целостности данных в блокчейне. Хранение секретных ключей в блокчейне обеспечивает аутентификацию участников, защиту от подделки и обеспечивает безопасность транзакций. Поэтому секретные ключи для цифровой подписи являются важным криптографическим компонентом в системе блокчейн.

![цифровая подпись](image/53.png){#fig:053 width=90%}

# Список литературы{.unnumbered}

::: {#refs}
:::