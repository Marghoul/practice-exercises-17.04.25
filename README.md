1. В ходе установки зависимостей обнаружил, что версии не совместимы. Версии были устаревшими, после обновления все исправилось. 

2. Разрешение конфликта зависимостей
Ситуация:
LibraryA требует LibraryC==1.0.0
LibraryB требует LibraryC==2.0.0
Решения:
Создать виртуальные окружения:

python -m venv envA
.\envA\Scripts\activate
pip install LibraryA
deactivate

python -m venv envB
.\envB\Scripts\activate
pip install LibraryB
deactivate

3. Установил с помощью команды npm i express lodash
Посмотрел версии с помощью команды npm package_name --version
lodash version: 10.9.0
express version: 10.9.0
Узнал минимальную версию пакета express при помощи команды npm view express versions (0.14.0)

4 - 6. Создал ветку feature, сейчас буду сливать ее воедино с main. 

Как видно в этом коде была ошибка c merge, я исправил ее.

Создал версии с помощью git tag. Добавил новую функцию в newfunction.py, создал новую версию. При каждом стабильном изменении проекта стоит заливать новую версию.

PS C:\Users\Lenovo\Desktop\margul> git init 

Initialized empty Git repository in C:/Users/Lenovo/Desktop/margul/.git/

PS C:\Users\Lenovo\Desktop\margul> git add .

warning: in the working copy of 'package-lock.json', LF will be replaced by CRLF the next time Git touches it

warning: in the working copy of 'package.json', LF will be replaced by CRLF the next time Git touches it

PS C:\Users\Lenovo\Desktop\margul> git commit -m "First-commit" 

[master (root-commit) e814c62] First-commit

 5 files changed, 854 insertions(+)
 
 create mode 100644 .gitignore
 
 create mode 100644 package-lock.json
 
 create mode 100644 package.json
 
 create mode 100644 requirements.txt
 
 create mode 100644 tasks.md
 
PS C:\Users\Lenovo\Desktop\margul> git checkout -b feature\

fatal: 'feature\' is not a valid branch name

hint: See `man git check-ref-format`

hint: Disable this message with "git config set advice.refSyntax false"

PS C:\Users\Lenovo\Desktop\margul> git checkout -b feature

Switched to a new branch 'feature'

PS C:\Users\Lenovo\Desktop\margul> git add .

PS C:\Users\Lenovo\Desktop\margul> git commit -m "tasks.md updated"

[feature 8bbb449] tasks.md updated

 1 file changed, 2 insertions(+), 1 deletion(-)
 
PS C:\Users\Lenovo\Desktop\margul> git checkout main

error: pathspec 'main' did not match any file(s) known to git

PS C:\Users\Lenovo\Desktop\margul> git checkout master

Switched to branch 'master'

PS C:\Users\Lenovo\Desktop\margul> git merge feature 

Updating e814c62..8bbb449

Fast-forward

 tasks.md | 3 ++-
 
 1 file changed, 2 insertions(+), 1 deletion(-)
 
PS C:\Users\Lenovo\Desktop\margul> git tag v1.0.0

>>
>>
PS C:\Users\Lenovo\Desktop\margul> git add .    

PS C:\Users\Lenovo\Desktop\margul> git commit -m "added new function"  

[master ab2f240] added new function

 1 file changed, 7 insertions(+)
 
 create mode 100644 newfunction.py
 
PS C:\Users\Lenovo\Desktop\margul> git tag v1.1.0

PS C:\Users\Lenovo\Desktop\margul> git add .

PS C:\Users\Lenovo\Desktop\margul> git commit -m "added new function2 "

[master f2a7d5c] added new function2

 1 file changed, 6 insertions(+)
 
PS C:\Users\Lenovo\Desktop\margul> git tag v1.1.1

PS C:\Users\Lenovo\Desktop\margul> git log --oneline --decorate

f2a7d5c (HEAD -> master, tag: v1.1.1) added new function2

ab2f240 (tag: v1.1.0) added new function

8bbb449 (tag: v1.0.0, feature) tasks.md updated

e814c62 First-commit

PS C:\Users\Lenovo\Desktop\margul> git tag

v1.0.0
v1.1.0
v1.1.1
PS C:\Users\Lenovo\Desktop\margul> git add .

PS C:\Users\Lenovo\Desktop\margul> git commit -m "final"

[master 1cb576b] final

 1 file changed, 59 insertions(+), 1 deletion(-)
 
PS C:\Users\Lenovo\Desktop\margul> git remote add origin https://github.com/Marghoul/practice-exercises-17.04.25.git

PS C:\Users\Lenovo\Desktop\margul> git branch -M master

PS C:\Users\Lenovo\Desktop\margul> git push -u origin master

info: please complete authentication in your browser...

Enumerating objects: 19, done.

Counting objects: 100% (19/19), done.

Delta compression using up to 8 threads

Compressing objects: 100% (17/17), done.

Writing objects: 100% (19/19), 10.04 KiB | 1.25 MiB/s, done.

Total 19 (delta 7), reused 0 (delta 0), pack-reused 0 (from 0)

remote: Resolving deltas: 100% (7/7), done.

To https://github.com/Marghoul/practice-exercises-17.04.25.git

 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

PS C:\Users\Lenovo\Desktop\margul> git branch 

* feature
  master
  
PS C:\Users\Lenovo\Desktop\margul> git push origin feature

Enumerating objects: 10, done.

Counting objects: 100% (10/10), done.

Delta compression using up to 8 threads

Compressing objects: 100% (8/8), done.

Writing objects: 100% (10/10), 8.63 KiB | 1.44 MiB/s, done.

Total 10 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)

remote: Resolving deltas: 100% (2/2), done.

remote: 
remote: Create a pull request for 'feature' on GitHub by visiting:

remote:      https://github.com/Marghoul/practice-exercises-17.04.25/pull/new/feature

remote:
To https://github.com/Marghoul/practice-exercises-17.04.25.git

 * [new branch]      feature -> feature
 * 
PS C:\Users\Lenovo\Desktop\margul> git push --tags

Enumerating objects: 7, done.

Counting objects: 100% (7/7), done.

Delta compression using up to 8 threads

Compressing objects: 100% (6/6), done.

Writing objects: 100% (6/6), 557 bytes | 557.00 KiB/s, done.

Total 6 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)

remote: Resolving deltas: 100% (3/3), completed with 1 local object.

To https://github.com/Marghoul/practice-exercises-17.04.25.git

 * [new tag]         v1.0.0 -> v1.0.0
 * [new tag]         v1.1.0 -> v1.1.0
 * [new tag]         v1.1.1 -> v1.1.1
PS C:\Users\Lenovo\Desktop\margul> git add .

PS C:\Users\Lenovo\Desktop\margul> git commit -m "updated"

[feature d54f2c9] updated

 1 file changed, 1 insertion(+), 1 deletion(-)
 
PS C:\Users\Lenovo\Desktop\margul> git checkout master 

Switched to branch 'master'

Your branch is up to date with 'origin/master'.

PS C:\Users\Lenovo\Desktop\margul> git merge feature 

Auto-merging tasks.md

CONFLICT (content): Merge conflict in tasks.md

Automatic merge failed; fix conflicts and then commit the result.

PS C:\Users\Lenovo\Desktop\margul> git merge feature

fatal: You have not concluded your merge (MERGE_HEAD exists).

Please, commit your changes before you merge.

PS C:\Users\Lenovo\Desktop\margul> git commit -m "updated"

[master 6cdacb4] updated

PS C:\Users\Lenovo\Desktop\margul> git merge feature

Already up to date.

PS C:\Users\Lenovo\Desktop\margul>
