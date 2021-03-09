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

   Команда: ```$ git commit -m"delete 'using namespace std;'."```
   
   Вывод(фрагмент):
   ```
   На ветке patch1
   Изменения, которые не в индексе для коммита:
     (используйте «git add/rm <файл>…», чтобы добавить или удалить файл из индекса)
     (use "git restore <file>..." to discard changes in working directory)
     (сделайте коммит или отмените изменения в неотслеживаемом или измененном содержимом в подмодулях)
	   изменено:      .bash_history
	   изменено:      .cache/mozilla/firefox/q9deefwq.default-release/cache2/entries/F98EB666F6B6A248B0B2E4914F8DC096FCAC8B94
	   изменено:      .cache/mozilla/firefox/q9deefwq.default-release/safebrowsing/google4/goog-badbinurl-proto.metadata
	   изменено:      .cache/mozilla/firefox/q9deefwq.default-release/safebrowsing/google4/goog-badbinurl-proto.vlpset
   ```
   
3. **commit**, **push** локальную ветку в удалённый репозиторий.

   Команда 1: ```$ git commit -m "Commit of branch."```
   
   Вывод(фрагмент):
   ```
   На ветке patch1
   Изменения, которые не в индексе для коммита:
     (используйте «git add/rm <файл>…», чтобы добавить или удалить файл из индекса)
     (use "git restore <file>..." to discard changes in working directory)
     (сделайте коммит или отмените изменения в неотслеживаемом или измененном содержимом в подмодулях)
   	изменено:      .bash_history
   	изменено:      .cache/mozilla/firefox/q9deefwq.default-release/cache2/entries/02EDB6AB71B49C0B0F6FE10B397CCF59B66D1B9E
   ```
   
   Команда 2: ```$ git checkout master.```
   
   Вывод(фрагмент):
   ```
   error: Ваши локальные изменения в указанных файлах будут перезаписаны при переключении на состояние:
	.bash_history
	.cache/mozilla/firefox/q9deefwq.default-release/cache2/entries/02EDB6AB71B49C0B0F6FE10B397CCF59B66D1B9E
	.cache/mozilla/firefox/q9deefwq.default-release/cache2/entries/09008055BF907CD3ACEA12412C83DD1A07D70976
	.cache/mozilla/firefox/q9deefwq.default-release/cache2/entries/09F7569B5528F1E701896973106E364BED786A5C
	.cache/mozilla/firefox/q9deefwq.default-release/cache2/entries/0ACA9C8486815ABAF991748A4990CB0448F4C3B6
	.cache/mozilla/firefox/q9deefwq.default-release/cache2/entries/0B78C8E599409E217F1D501D0BDE15213FF3F0BB
	.cache/mozilla/firefox/q9deefwq.default-release/cache2/entries/0DDCED7BD9D8235DE0A1FCCF69235CE8F84669D3
	.cache/mozilla/firefox/q9deefwq.default-release/cache2/entries/1241A9551D328553E43831E9D9C55B87DD2AE103
   ```
      
4. Проверьте, что ветка ```patch1``` доступна в удалёный репозитории.

   Команда: ```$ git remote```

   Вывод: ```origin```
   
5. Создайте ```pull-request patch1 -> master```.

   --
