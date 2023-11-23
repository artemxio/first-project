# BASH tips<br>

cd – сменить директорию<br>
&emsp; ~ домашняя директория<br>
&emsp; .. на уровень выше<br>
&emsp;. текущая директория (когда нужно запустить скрипт и передать папку в качестве параметра)<br>

pwd – показать путь текущей директории<br>
ls – показать файлы текущей директории<br>
&emsp; -la в виде списка<br>
&emsp; -а – все, включая скрытые (начинаются с .)<br>

touch – создать файл<br>
mkdir – создать директорию<br>
&emsp; -p создать структуру директорий<br>

cp – копирование файлов<br>
mv – перемещение файлов и папок<br>
cat – чтение файлов<br>
rm, rmdir, rm - r – удаление файлов и папок<br>
&emsp; && – несколько команд<br>

git config – конфигурация git<br>
&emsp; git config --global user.name "User Namovich" # имя или ник нужно написать латиницей и в  кавычках<br>

git init – создание репозитория в папке<br>
rm -rf .git - разгитить<br>
&emsp; ключ -r (от англ. recursive — «рекурсивно») позволяет удалять папки вместе с их содержимым;<br>
&emsp; ключ -f (от англ. force — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?».<br>

git status – проверить состояние репозитория<br>
git add – подготовить файлы к сохранени. Пример git add --all (добавить все файлы) git add . (добавить всю текущую папку)<br>
git commit – выполнить коммит<br>
&emsp; -m – добавить сообщение (комментарий)<br>

clip < ~/.ssh/id_ed25519.pub – скопировать содержимое файла с ключом в буфер<br>
git log – история коммитов<br>
&emsp; --oneline - сокращенный лог
git config --global user.email username@yandex.ru # здесь нужно указать свой настоящий email<br>
ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" – создать ключ<br>
git remote add – привязать удаленный репозиторий к локальному<br>
git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git<br>
&emsp; Где origin – имя удаленного репозитория<br>

git remote –v – убедиться, что репозитории связаны<br>
git push -u origin main – первый пуш. Где origin имя удаленного репозитория, а main (master) – название текущей ветки. -u связывает удаленную ветку и локальную<br>
&emsp; --force - принудительный пуш, если обновляемая ветка в репозитории старше, чем в локальном (например, был откат коммита)

git commit --amend --no-edit  - обновить/исправить последний коммит (внести изменения без добавления нового коммита)<br>
git commit --amend -m - изменить сообщение коммита<br>
git restore --staged <file> - выполнить unstage изменений (до коммита)<br>
git reset --hard <commit hash> - откат к указанному коммиту<br>
git restore <file> - откатить изменения, которые не попали ни в staging, ни в коммит (если случайно отредактирован файл и теперь попал в modified)<br>
git diff - посмотреть какие изменения были сделаны в коммите<br>
&emsp; staged - посмотреть изменения в staged (после add)<br>
.gitignore - файл, в котором можно перечислить файлы, которые не должны трекаться, например:<br>

&emsp;.DS_Store<br>

&emsp; # игнорировать все файлы, которые заканчиваются на .jpeg<br>
&emsp; *.jpeg<br>

&emsp; # игнорировать все файлы "tmp" во всех подпапках папки docs<br>
&emsp; docs/*/tmp<br>

&emsp; # игнорировать файлы file0.txt, file1.txt и file2.txt<br>
&emsp; # при этом не игнорировать file3.txt, file4.txt, ...<br>
&emsp; file[0-2].txt <br>

&emsp; file?.txt - будут проигнорированы, например, файлы fileA.txt и file1.txt. А вот файл file12.txt не будет проигнорирован, потому что в его названии два символа после file, а не один.<br>

&emsp; # игнорировать todo.txt в корне репозитория<br>
&emsp; /todo.txt<br>

&emsp; # для сравнения: spam.txt будет игнорироваться во всех папках<br>
&emsp; spam.txt<br>

&emsp; # игнорировать папку build<br>
&emsp; build/ <br>

&emsp; # игнорировать файлы "docs/current/tmp", "docs/old/tmp",<br>
&emsp; # а также "docs/old/saved/a/b/c/d/tmp"<br>
&emsp; # и даже "docs/tmp", потому что ноль вложенных папок тоже подходит<br>
&emsp; docs/**/tmp<br>

&emsp; # игнорировать только "docs/current/tmp" и "docs/old/tmp"<br>
&emsp; # файл "docs/old/saved/a/b/c/d/tmp" не попадает в правило<br>
&emsp; docs/*/tmp <br>

&emsp; # игнорировать все JPEG-файлы<br>
&emsp; *.jpeg<br>

&emsp; # но только не мем с Doge<br>
&emsp; !doge.jpeg <br>

&emsp; !# игнорировать все файлы в каталоге build<br>
&emsp; !build/<br>

&emsp; !# игнорировать все .log файлы<br>
&emsp; !*.log<br>
 
&emsp; !# не игнорировать *.log файлы в examples<br>
&emsp; !# потому что это пример для документации<br>
&emsp; !!examples/**/*.log <br>

git status --ignored - отобразить игнорируемые файлы<br>

Пример mermaid-схемы:<br>

test

```mermaid
graph LR;
  untracked -- "git add" --> staged;
  staged    -- "???"     --> tracked/comitted;

%% стрелка без текста для примера: 
  A --> B;
``` 
