---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Git"
subtitle: "Программное обеспечение для отслеживания изменений."
summary: "Сообщение о git"
authors: [Khoshkhoev. A. B.]
tags: []
categories: []
date: 2022-05-06T18:48:37+03:00
lastmod: 2022-05-06T18:48:37+03:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

![](https://fuzeservers.ru/wp-content/uploads/4/c/a/4ca54660353facf2dab077639fb18a8b.png)

## Обзор

Git (/git/) - это программное обеспечение для отслеживания изменений в любом наборе файлов, обычно используемое для координации работы программистов, совместно разрабатывающих исходный код во время разработки программного обеспечения. Его цели включают скорость, целостность данных и поддержку распределенных нелинейных рабочих процессов (тысячи параллельных ветвей, работающих в разных системах).

Git был первоначально создан Линусом Торвальдсом в 2005 году для разработки ядра Linux, а другие разработчики ядра внесли свой вклад в его первоначальную разработку. С 2005 года Джунио Хамано является основным сопровождающим. Как и в большинстве других распределенных систем контроля версий, и в отличие от большинства клиент-серверных систем, каждый каталог Git на каждом компьютере представляет собой полноценное хранилище с полной историей и возможностями отслеживания версий, независимо от доступа к сети или центрального сервера. Git - это бесплатное программное обеспечение с открытым исходным кодом, распространяемое только по лицензии GPL-2.0.

## История 

Разработка Git началась в апреле 2005 года, после того, как многие разработчики ядра Linux отказались от доступа к BitKeeper, проприетарной системе управления версиями (SCM), которую они использовали для поддержки проекта с 2002 года. Владелец авторских прав на BitKeeper Ларри Маквой отказался от бесплатного использования продукта после заявления о том, что Эндрю Тридджелл создал SourcePuller путем обратного проектирования протоколов BitKeeper. Тот же инцидент также послужил толчком к созданию другой системы контроля версий, Mercurial.

Линус Торвальдс хотел иметь распределенную систему, которую он мог бы использовать, как BitKeeper, но ни одна из доступных бесплатных систем не удовлетворяла его потребностям. Торвальдс привел пример системы управления версиями, которой требуется 30 секунд, чтобы применить исправление и обновить все связанные метаданные, и отметил, что это не будет соответствовать потребностям разработки ядра Linux, где синхронизация с другими сопровождающими может потребовать 250 таких действий одновременно. Для своего критерия дизайна он указал, что исправление должно занимать не более трех секунд, и добавил еще три цели:

Возьмем систему параллельных версий (CVS) в качестве примера того, чего не следует делать; если вы сомневаетесь, примите прямо противоположное решение.
Поддерживайте распределенный рабочий процесс, подобный BitKeeper.
Включите очень строгие гарантии против коррупции, будь то случайной или злонамеренной.
Эти критерии исключали все системы контроля версий, которые использовались в то время, поэтому сразу после выпуска версии 2.6.12-rc2 для разработки ядра Linux Торвальдс решил написать свою собственную.

Разработка Git началась 3 апреля 2005 года. Торвальдс объявил о проекте 6 апреля и на следующий день стал самостоятельным хостингом. Первое слияние нескольких филиалов состоялось 18 апреля. Торвальдс достиг своих целей по производительности; 29 апреля зарождающийся Git был протестирован на запись исправлений в дерево ядра Linux со скоростью 6,7 исправлений в секунду. 16 июня Git управлял выпуском ядра 2.6.12.

26 июля 2005 года Торвальдс передал техническое обслуживание Джунио Хамано, одному из основных участников проекта. Хамано был ответственен за выпуск версии 1.0 21 декабря 2005 года и остается основным сопровождающим проекта.

## Дизайн

Дизайн Git был вдохновлен BitKeeper и Monotone. Git изначально разрабатывался как низкоуровневый движок системы управления версиями, поверх которого другие могли бы писать интерфейсы, такие как Cogito или StGit. С тех пор основной проект Git превратился в полноценную систему контроля версий, которую можно использовать напрямую. Находясь под сильным влиянием BitKeeper, Торвальдс сознательно избегал традиционных подходов, что привело к уникальному дизайну.

## Реализации

Git (основная реализация на C) в основном разрабатывается для Linux, хотя он также поддерживает большинство основных операционных систем, включая BSD (DragonFly BSD, FreeBSD, NetBSD и OpenBSD), Solaris, macOS и Windows.

Первый порт Git для Windows был в первую очередь платформой эмуляции Linux, в которой размещалась версия Linux. Установка Git под Windows создает каталог Program Files с аналогичным именем, содержащий порт Mingw-w64 коллекции компиляторов GNU, Perl 5, MSYS2 (сам по себе является форком Cygwin, Unix-подобной среды эмуляции для Windows) и различные другие порты Windows или эмуляции утилит и библиотек Linux. В настоящее время собственные сборки Git для Windows распространяются в виде 32- и 64-разрядных установщиков. На официальном сайте git в настоящее время поддерживается сборка Git для Windows, по-прежнему использующая среду MSYS2.

JGit-реализация Git - это чистая программная библиотека Java, предназначенная для встраивания в любое Java-приложение. JGit используется в инструменте проверки кода Gerrit и в EGit, клиенте Git для Eclipse IDE.

Go-git - это реализация Git с открытым исходным кодом, написанная на чистом Go. В настоящее время он используется для резервного копирования проектов в качестве интерфейса SQL для репозиториев кода Git и обеспечивает шифрование для Git.

Реализация Git в Далвиче - это чисто программный компонент Python для Python 2.7, 3.4 и 3.5.

Реализация Git libgit2 представляет собой программную библиотеку ANSI C без каких-либо других зависимостей, которая может быть создана на нескольких платформах, включая Windows, Linux, macOS и BSD. Он имеет привязки для многих языков программирования, включая Ruby, Python и Haskell.

JS-Git - это реализация JavaScript подмножества Git.

## Безопасность

Git не предоставляет механизмов контроля доступа, но был разработан для работы с другими инструментами, которые специализируются на контроле доступа.

17 декабря 2014 года был обнаружен эксплойт, влияющий на версии клиента Git для Windows и macOS. Злоумышленник может выполнить произвольное выполнение кода на целевом компьютере с установленным Git, создав вредоносное дерево Git (каталог) с именем .git (каталог в репозиториях Git, в котором хранятся все данные репозитория) в другом случае (например, .GIT или .Git, необходим, потому что Git не позволяет создавать все строчные версии .git вручную) с вредоносными файлами в подкаталоге .git/hooks (папка с исполняемыми файлами, которые запускает Git) в репозитории, созданном злоумышленником, или в репозитории, который злоумышленник может изменить. Если пользователь Windows или Mac извлекает (загружает) версию репозитория с вредоносным каталогом, а затем переключается на этот каталог, каталог .git будет перезаписан (из-за нечувствительности к регистру файловых систем Windows и Mac), а вредоносные исполняемые файлы в .git/hooks могут быть run, что приводит к выполнению команд злоумышленника. Злоумышленник также может изменить конфигурационный файл .git/config, который позволяет злоумышленнику создавать вредоносные псевдонимы Git (псевдонимы для команд Git или внешних команд) или изменять существующие псевдонимы для выполнения вредоносных команд при запуске. Уязвимость была исправлена в версии 2.2.1 Git, выпущенной 17 декабря 2014 года, и анонсирована на следующий день.

Версия Git 2.6.1, выпущенная 29 сентября 2015 года, содержала исправление для уязвимости в системе безопасности (CVE-2015-7545), которая допускала выполнение произвольного кода. Уязвимость можно было использовать, если злоумышленник мог убедить жертву клонировать определенный URL-адрес, поскольку произвольные команды были встроены в сам URL-адрес. Злоумышленник мог использовать эксплойт с помощью атаки "человек посередине", если соединение было незашифрованным, поскольку он мог перенаправить пользователя на URL-адрес по своему выбору. Рекурсивные клоны также были уязвимы, поскольку они позволяли контроллеру репозитория указывать произвольные URL-адреса через файл gitmodules.

Git использует внутренние хэши SHA-1. Линус Торвальдс ответил, что хэш был в основном предназначен для защиты от случайного повреждения, а безопасность, которую обеспечивает криптографически защищенный хэш, была просто случайным побочным эффектом, а основной защитой была подпись в другом месте. После демонстрации атаки SHAttered на git в 2017 году git был модифицирован для использования варианта SHA-1, устойчивого к этой атаке. План перехода на хэш-функцию разрабатывается с февраля 2020 года.