
# Что такое Git Bash?
---
Git Bash — это приложение для сред Microsoft Windows, эмулирующее работу командной строки Git. Bash — аббревиатура от Bourne Again Shell. Оболочка (Shell) представляет собой приложение терминала для взаимодействия с операционной системой с помощью письменных команд. Bash — популярная оболочка, используемая по умолчанию в Linux и macOS. Git Bash представляет собой пакет, который устанавливает в операционную систему Windows оболочку Bash, некоторые распространенные утилиты Bash и систему Git.

---


# Что делает команда git pull? Чем она отличается от git push?
---

**git pull** - используется для извлечения и загрузки содержимого из удаленного репозитория и немедленного обновления локального репозитория этим содержимым. Выполнение git pull, как правило, извлекает (fetch) данные с сервера, с которого вы изначально клонировали, и автоматически пытается слить (merge) их с кодом, над которым вы в данный момент работаете.

**git push** - используется для выгрузки содержимого локального репозитория в удаленный репозиторий. Она позволяет передать коммиты из локального репозитория в удаленный. Эта команда симметрична команде git fetch: при извлечении с помощью fetch коммиты импортируются в локальные ветки, а при публикации с помощью push коммиты экспортируются в удаленные ветки. 

---

# Что такое merge request?

---
Merge requests — основной способ внесения изменений в код при использовании GitLab. Изменения вносятся в код, затем автором изменений создаётся merge request, который затем обсуждается, в котором происходит code review. Merge request в результате принимается, отправляется на доработку или отклоняется.

---

# Чем между собой отличаются команды git status и git log?

---

**git status** показывает состояния файлов в рабочей директории и индексе: какие файлы изменены, но не добавлены в индекс; какие ожидают коммита в индексе. Вдобавок к этому выводятся подсказки о том, как изменить состояние файлов.

**git log**  используется для просмотра истории коммитов, начиная с самого свежего и уходя к истокам проекта. По умолчанию, она показывает лишь историю текущей ветки, но может быть настроена на вывод истории других, даже нескольких сразу, веток. Также её можно использовать для просмотра различий между ветками на уровне коммитов.

---

# Что такое submodule? С помощью какой команды можно добавлять сабмодули в свой репозиторий?

---

Часто при работе над проектом, возникает необходимость использовать в нём другой проект. Типичная проблема, возникающая при этом — необходимость продолжать работать с двумя проектами по отдельности, но при этом использовать один из них в другом.

Git решает эту проблему с помощью подмодулей. Подмодули позволяют сохранить один Git-репозиторий, как подкаталог другого Git-репозитория. Это даёт возможность клонировать в ваш проект другой репозиторий, но коммиты при этом хранить отдельно.

Для добавления нового подмодуля используйте команду **git submodule add**, указав относительный или абсолютный URL проекта, который вы хотите начать отслеживать.

---

