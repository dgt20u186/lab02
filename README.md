# lab02
## Далгатов Гитиномагомед, ИУ8-22

### Part 1
1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).

   Команда: ```$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab02.git```
  
2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.

   Команда: ``` git commit -a -m"Commit message."```
  
   Вывод:
   ```
   На ветке master
 
   Начальный коммит

   Неотслеживаемые файлы:
     (используйте «git add <файл>…», чтобы добавить в то, что будет включено в коммит)
 	  REPORT.md

   ничего не добавлено в коммит, но есть неотслеживаемые файлы (используйте «git add», чтобы отслеживать их)
   ```
  
3. Создайте файл ```hello_world.cpp``` в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу **Hello world** на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку ```using namespace std;```

   Команда: ```$ cat > hello_world.cpp <<EOF```
   ```
   > #include <iostream>
   > 
   > using namespace std;
   > 
   > int main()
   > {
   >     cout << "Hello world!";
   >     return 0;
   > }
   > EOF
   ```

4. Добавьте этот файл в локальную копию репозитория.

   Команда: ```$ git add hello_world.cpp```
  
5. Закоммитьте изменения с *осмысленным* сообщением.

   Команда: ```$ git commit -m"added hello_world.cpp"```
  
   Вывод:
   ```
   [master (корневой коммит) 93c3367] added hello_world.cpp
   1 file changed, 9 insertions(+)
   create mode 100644 hello_world.cpp
   ```
  
6. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение ```Hello world from @name```, где ```@name``` имя пользователя.

   Команда: ```$ cat > hello_world.cpp <<EOF```
   ```
   > #include <iostream>
   > #include <string>
   > 
   > using namespace std;
   > 
   > int main()
   > {
   >     string name;
   >     cout << "Input your name: ";
   >     cin.ignore();
   >     getline(cin, name);
   >     cout << "Hello world from "" << name;
   >     return 0;
   > }
   > EOF
   ```
   
7. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно ```git add```?

   Команда: ```$ git commit -a -m"added hello_world.cpp."```

   Вывод:
   ```
   [master edb4a61] added hello_world.cpp.
   1 file changed, 7 insertions(+), 2 deletions(-)
   ```

8. Запуште изменения в удалёный репозиторий.

   Команда: ```$ git push origin master```
   
   Вывод:
   ```
   Username for 'https://github.com': dgt20u186
   Password for 'https://dgt20u186@github.com': 
   remote: Repository not found.
   fatal: repository 'https://github.com//lab02.git/' not found
   ```
   
9. Проверьте, что история коммитов доступна в удалёный репозитории.

   Команда: ```$ git log```
   
   Вывод:
   ```
   commit edb4a61faaf3d1a3fc2a87c942d4ec96edd24f1b (HEAD -> master)
   Author: dgt20u186 <dalgatovgitinomd@gmail.com>
   Date:   Mon Mar 8 12:17:56 2021 +0300

       added hello_world.cpp.

   commit 16155c555ed8fdad102e68d15e36007d101de146
   Author: dgt20u186 <dalgatovgitinomd@gmail.com>
   Date:   Mon Mar 8 12:13:22 2021 +0300

       added hello_world.cpp
   ```


### Part 2
1. В локальной копии репозитория создайте локальную ветку ```patch1```.

   Команда: ```$ git checkout -b patch1```
   
   Вывод: ```Переключено на новую ветку «patch1»```
   
2. Внесите изменения в ветке ```patch1``` по исправлению кода и избавления от ```using namespace std;```.

   Команда: 
   
