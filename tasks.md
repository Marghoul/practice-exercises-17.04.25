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

4. Создал ветку feature, сейчас буду сливать ее воедино main