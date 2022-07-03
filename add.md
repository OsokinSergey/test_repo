# Наименование
`git add` - добавляет файл для отслеживания
# Обзор
git add [--verbose | -v] [--dry-run | -n] [--force | -f] [--interactive | -i] [--patch | -p] [--edit | -e] [--[no-]all | --[no-]ignore-removal | [--update | -u]] [--sparse] [--intent-to-add | -N] --refresh] [--ignore-errors] [--ignore-missing] [--renormalize] [--chmod=(+|-)x] [--pathspec-from-file=<file> [--pathspec-file-nul]] [--] [<pathspec>…​]
# Описание
Эта команда обновляет индекс, используя текущее содержимое, найденное в рабочем дереве, чтобы подготовить содержимое к следующему коммиту. Обычно она добавляет текущее содержимое существующих путей целиком, но с некоторыми опциями ее можно использовать для добавления содержимого с применением только части изменений, внесенных в файлы рабочего дерева, или для удаления путей, которые больше не существуют в рабочем дереве.

В "индексе" хранится снимок содержимого рабочего дерева, и именно этот снимок берется в качестве содержимого следующего коммита. Таким образом, после внесения изменений в рабочее дерево и перед выполнением команды commit, вы должны использовать команду add, чтобы добавить все новые или измененные файлы в индекс.

Эта команда может быть выполнена несколько раз перед фиксацией. Она добавляет содержимое указанного файла(ов) только в момент выполнения команды add; если вы хотите, чтобы последующие изменения были включены в следующий коммит, то вам нужно снова выполнить git add, чтобы добавить новое содержимое в индекс.

Команду git status можно использовать для получения сводки о том, в каких файлах есть изменения, поставленные на следующую фиксацию.

По умолчанию команда git add не добавляет игнорируемые файлы. Если какие-либо игнорируемые файлы были явно указаны в командной строке, git add выдаст ошибку со списком игнорируемых файлов. Игнорируемые файлы, достигнутые в результате рекурсии каталогов или глобирования имен файлов, выполняемого Git'ом (заключайте глобы в кавычки перед shell'ом), будут молча проигнорированы. Команда git add может быть использована для добавления игнорируемых файлов с опцией -f (force).