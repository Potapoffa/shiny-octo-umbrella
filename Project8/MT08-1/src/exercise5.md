# PowerShell
## Что такое PowerShell?
PowerShell — это современная командная оболочка, в которой реализованы лучшие возможности других популярных оболочек. В отличие от большинства оболочек, которые только принимают и возвращают текст, PowerShell принимает и возвращает объекты .NET.
## Какие возможности имеет PowerShell?
следующие возможности:

- надежный журнал командной строки;
- заполнение нажатием клавиши TAB и  подстановка команд ;
- поддержка псевдонимов команд и параметров;
- создание конвейера для объединения команд;
- система справки в консоли, похожая на страницы man в Unix.
## Как открыть журнал событий в PowerShell?
На данный момент в Windows доступны два командлета для доступа к событиям в Event Log: Get-EventLog и Get-WinEvent. В подавляющем большинстве случаев рекомендуем использовать именно Get-WinEvent, т.к. он более производителен, особенно в сценариях обработки большого количества событий с удаленных компьютеров. Командлет Get-EventLog является устаревшим и использовался для получения логов в более ранних версиях Windows. Кроме того, Get-EventLog не поддерживается в современных версиях PowerShell Core 7.x.

Для использования команды Get-WinEvent нужно запустить PowerShell с правами администратора (при запуске Get-WinEvent от имени пользователя вы не сможете получить доступ к некоторым логам, например, к Security).
## Чем cmd отличается от PowerShell?
Главное отличие между PowerShell и CMD является то, что PowerShell — это мощный интерфейс командной строки и среда сценариев, которая позволяет выполнять сложные сценарии для простого и эффективного выполнения задач администрирования системы Windows, а CMD — интерфейс командной строки, который предоставляет пользователю набор команд для взаимодействия с компьютером для выполнения задач.

Ключевым отличием от CMD, заметным на старте работы, являются командлеты — упрощенные команды, используемые в среде PowerShell. Назначение команды PowerShell довольно легко интерпретировать по названию: они следуют простой закономерности — за глаголом идет существительное.

Сравним:

- Команда CMD: ping
- Командлет PowerShell: Test-Connection

Командлеты помогают управлять инфраструктурой Windows. Кроме того, они позволяют обычному пользователю получить удаленный доступ к реестру, файловой системе и пространству Windows Management Instrumentation (WMI) на системах.

Как современная командная оболочка PowerShell включает в себя лучшие функции других популярных оболочек. В отличие от большинства оболочек, которые принимают и возвращают только текст, PowerShell принимает и возвращает объекты .NET. Это программная платформа, в которой исполняются программы. Таким образом, нет необходимости разбирать текст для извлечения информации из выходных данных.

Как язык сценариев PowerShell обычно используется для автоматизации управления системами, позволяет создавать сложные сценарии с множеством условий. Он также используется для сборки, тестирования и развертывания решений, часто в средах CI/CD.

Открыть shell, как и командную строку, можно через поисковую строку и через меню выполнения, вписав в обоих случаях PowerShell. Также, в зависимости от версии операционной системы его можно найти в Power User Menu. Открывается оно комбинацией клавиш win+x или нажатием правой кнопки мыши на значок Windows.

Разница PowerShell и CMD заключается в их использовании. Последний используется в основном для выполнения пакетных команд, устранения некоторых первичных неполадок. PowerShell, в свою очередь, может использоваться как для выполнения пакетных команд, так и для административных целей.

Важной является возможность создания сценариев (скриптов) — текстовых файлов, содержащих всего одну или целый набор команд PowerShell.
## Какой командой в PowerShell можно просмотреть список доступных журналов событий?
 Список доступных журналов можно получить командой Get-WinEvent -ListLog.Получает события из журналов событий и файлов журналов трассировки событий на локальных и удаленных компьютерах.Командлет получает данные из журналов событий, созданных технологией журнала событий Windows, представленной в Windows Vista, и событиями в файлах журнала, созданных трассировкой событий Windows (ETW). По умолчанию Get-WinEvent возвращает сведения о событии в порядке от новейших к старым.

 Чтобы прервать выполнение команды, нажмите клавиши CTRL+C. События можно получить из выбранных журналов или из журналов, созданных выбранными поставщиками событий. Кроме того, можно объединять события из нескольких источников в одну команду. Get-WinEvent позволяет фильтровать события с помощью запросов XPath, структурированных XML-запросов и запросов хэш-таблиц.

 Если вы не используете PowerShell от имени администратора, могут появиться сообщения об ошибках, указывающие на то, что вы не можете получить сведения о журнале.
## Какой командой можно узнать текущую версию PowerShell?
Для того, чтобы узнать текущую версию PowerShell, нужно выполнить команду:

$PSVersionTable.

Как видно из результата выполнения команды в строке PSVersion стоит значение 5.0.

Для переключения в другую версию PowerShell выполните команду:

PowerShell.exe –version {номер версии}