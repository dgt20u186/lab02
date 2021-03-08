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

   Команда: ```$ git commit -m"hello_world.cpp is updated."```

   Вывод:
   ```
   На ветке master

   Начальный коммит

   Неотслеживаемые файлы:
     (используйте «git add <файл>…», чтобы добавить в то, что будет включено в коммит)
   	   .bash_history
   	   .bash_logout
	   .bashrc
	   .cache/
	   .config/
	   .gem/
	   .gist
	   .gitconfig
	   .local/
	   .mozilla/
	   .pki/
	   .profile
	   .sudo_as_admin_successful
	   .viminfo
	   .vscode/
	   .wget-hsts
	   boost_1_69_0.tar.gz.1
	   boost_1_69_0/
	   dgt20u186/
	   hello_world.cpp
	   include
	   snap/
	   token/
	   workspace/
	   "\320\227\320\260\320\263\321\200\321\203\320\267\320\272\320\270/"
	   "\320\230\320\267\320\276\320\261\321\200\320\260\320\266\320\265\320\275\320\270\321\217/"

   ничего не добавлено в коммит, но есть неотслеживаемые файлы (используйте «git add», чтобы отслеживать их)
   ```

