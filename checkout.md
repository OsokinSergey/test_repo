# Наименование
`git chekout` - Переключение ветвей или восстановление файлов рабочего дерева 
# Обзор
`git checkout` [-q] [-f] [-m] [< branch >]

`git checkout` [-q] [-f] [-m] --detach [< branch >]

`git checkout` [-q] [-f] [-m] [--detach] < commit >

`git checkout` [-q] [-f] [-m] [[-b|-B|--orphan] < new-branch >] [< start-point >]

`git checkout` [-f|--ours|--theirs|-m|--conflict=< style >] [< tree-ish >] [--] < pathspec >…​

`git checkout` [-f|--ours|--theirs|-m|--conflict=< style >] [< tree-ish >] --pathspec-from-file=< file > [--pathspec-file-nul]

`git checkout` (-p|--patch) [< tree-ish >] [--] [< pathspec >…​]
# Описание
Обновляет файлы в рабочем дереве в соответствии с версией в индексе или указанном дереве. Если pathspec не был указан, git checkout также обновит HEAD, чтобы установить указанную ветвь в качестве текущей.

`git checkout` [< branch >]

Чтобы подготовиться к работе над <branch>, переключитесь на неё, обновив индекс и файлы в рабочем дереве, а также указав HEAD на эту ветвь. Локальные модификации файлов в рабочем дереве сохраняются, чтобы их можно было зафиксировать в <branch>.Если <branch> не найдена, но существует отслеживаемая ветвь ровно в одном удаленном месте (назовем его <remote>) с подходящим именем, и не указано --no-guess, то рассматривается как эквивалент

`git checkout` -b|-B <новая ветвь> [<пусковая точка>].

Указание -b приводит к созданию новой ветви, как если бы была вызвана git-branch[1], а затем произведена проверка. В этом случае вы можете использовать опции --track или --no-track, которые будут переданы git branch. Для удобства, --track без -b подразумевает создание ветки; см. описание --track ниже. Если указано -B, < new-branch > будет создана, если она не существует; в противном случае она будет сброшена. Это транзакционный эквивалент

`git branch` -f < branch > [< start-point >]

`git checkout` < branch >

то есть ветка не сбрасывается/создается, пока "git checkout" не будет успешным.

`git checkout` --detach [< branch >]

`git checkout` [--detach] < commit >

Подготовиться к работе поверх < commit >, отсоединив HEAD на нём (см. раздел "DETACHED HEAD"), и обновить индекс и файлы в рабочем дереве. Локальные модификации файлов в рабочем дереве сохраняются, так что результирующее рабочее дерево будет состоянием, записанным в коммите, плюс локальные модификации.
Когда аргументом < commit > является имя ветви, опция --detach может быть использована для отсоединения HEAD на вершине ветви (git checkout < branch > проверит эту ветвь без отсоединения HEAD).
Если опустить < branch >, HEAD будет отсоединен в конце текущей ветки.

`git checkout` [-f|--ours|--theirs|-m|--conflict=< style >] [< tree-ish >] [--] < pathspec >...

`git checkout` [-f|--ours|--theirs|-m|--conflict=< style >] [< tree-ish >] --pathspec-from-file=< file > [--pathspec-file-nul]

Перезаписывает содержимое файлов, соответствующих pathspec. Если < tree-ish > (чаще всего это фиксация) не задано, перезаписывает рабочее дерево содержимым в индексе. Если указано < tree-ish >, перезаписать и индекс, и рабочее дерево содержимым на < tree-ish >.
Индекс может содержать неперезаписанные записи из-за предыдущего неудачного слияния. По умолчанию, если вы попытаетесь извлечь такую запись из индекса, операция извлечения завершится неудачей, и ничего не будет извлечено. Использование параметра -f позволяет игнорировать эти неразмеченные записи. Содержимое определённой стороны слияния может быть вычеркнуто из индекса с помощью --ours или --theirs. С помощью -m изменения, внесённые в файл рабочего дерева, могут быть отброшены, чтобы воссоздать исходный результат слияния с конфликтом.

`git checkout` (-p|--patch) [< tree-ish >] [--] [< pathspec >...].

Этот режим похож на предыдущий, но позволяет вам использовать интерактивный интерфейс для отображения вывода "diff" и выбора того, какие hunks использовать в результате.