Консольные команды<br>
cd – сменить директорию<br>


~ домашняя директория<br>


.. на уровень выше<br>


. текущая директория (когда нужно запустить скрипт и передать папку в качестве параметра)<br>
pwd – показать путь текущей директории<br>
ls – показать файлы текущей директории<br>


-la в виде списка<br>


-а – все, включая скрытые (начинаются с .)<br>
touch – создать файл<br>
mkdir – создать директорию<br>


-p создать структуру директорий<br>
cp – копирование файлов<br>
mv – перемещение файлов и папок<br>
cat – чтение файлов<br>
rm, rmdir, rm - r – удаление файлов и папок<br>


&& – несколько команд<br>
git config – конфигурация git<br>


git config --global user.name "User Namovich" # имя или ник нужно написать латиницей и в  кавычках<br>
git init – создание репозитория в папке<br>
rm -rf .git - разгитить<br>


ключ -r (от англ. recursive — «рекурсивно») позволяет удалять папки вместе с их содержимым;<br>


ключ -f (от англ. force — «заставить») избавит вас от вопросов вроде «Вы точно хотите удалить этот файл? А этот? И этот тоже?».<br>
git status – проверить состояние репозитория<br>
git add – подготовить файлы к сохранени. Пример git add --all (добавить все файлы) git add . (добавить всю текущую папку)<br>
git commit – выполнить коммит<br>


-m – добавить сообщение (комментарий)<br>
clip < ~/.ssh/id_ed25519.pub – скопировать содержимое файла с ключом в буфер<br>
git log – история коммитов<br>
git config --global user.email username@yandex.ru # здесь нужно указать свой настоящий email<br>
ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub" – создать ключ<br>
git remote add – привязать удаленный репозиторий к локальному<br>
git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git<br>


Где origin – имя удаленного репозитория<br>
git remote –v – убедиться, что репозитории связаны<br>
git push -u origin main – первый пуш. Где origin имя удаленного репозитория, а main – название текущей ветки. -u связывает удаленную ветку и локальную<br>
