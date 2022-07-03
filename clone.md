# Наименование
`git clone` - Клонирование хранилища в новый каталог
# Обзор
`git clone` [--template=<template-directory>]
	  [-l] [-s] [--no-hardlinks] [-q] [-n] [--bare] [--mirror]
	  [-o <name>] [-b <name>] [-u <upload-pack>] [--reference <repository>]
	  [--dissociate] [--separate-git-dir <git-dir>]
	  [--depth <depth>] [--[no-]single-branch] [--no-tags]
	  [--recurse-submodules[=<pathspec>]] [--[no-]shallow-submodules]
	  [--[no-]remote-submodules] [--jobs <n>] [--sparse] [--[no-]reject-shallow]
	  [--filter=<filter> [--also-filter-submodules]] [--] <repository>
	  [<directory>]
# Описание

Клонирует репозиторий во вновь созданный каталог, создает ветви удаленного отслеживания для каждой ветви клонированного репозитория (видимые с помощью git branch --remotes), а также создает и проверяет начальную ветвь, форкнутую из текущей активной ветви клонированного репозитория.

После клонирования обычная git fetch без аргументов обновит все удаленные отслеживаемые ветви, а git pull без аргументов дополнительно объединит удаленную мастер-ветвь с текущей мастер-ветвью, если таковая имеется (это неверно, если задано "--single-branch"; см. ниже).

Эта конфигурация по умолчанию достигается путём создания ссылок на удалённые ветки в разделе refs/remotes/origin и инициализации конфигурационных переменных remote.origin.url и remote.origin.fetch.

Переведено с помощью www.DeepL.com/Translator (бесплатная версия)