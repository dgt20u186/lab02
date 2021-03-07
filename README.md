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
  
6. 
