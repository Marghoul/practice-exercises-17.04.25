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

4. Создал ветку feature, сейчас буду сливать ее воедино с main

Снизу прикрепил задание с 4 по 6

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

PS C:\Users\Lenovo\Desktop\margul> 

