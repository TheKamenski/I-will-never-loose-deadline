##Дополнительное задание 

```sh
  ~ ❯ git clone git@github.com:TheKamenski/I-will-never-loose-deadline.git
Клонирование в «I-will-never-loose-deadline»...
warning: Похоже, что вы клонировали пустой репозиторий.
  ~ ❯ ls        
bin                          lab01  tasks        TOKEN.md
I-will-never-loose-deadline  lab02  TheKamenski  Загрузки
  ~ ❯ cd I-will-never-loose-deadline 

```

Пишем прогу

```sh
  ~/I-will-never-loose-deadline   main ❯ cat > main.cpp <<EOF       
#include <iostream>

int main() {
    int num;
    std::cout << "Enter a number: ";
    std::cin >> num;

    while (num!=0) {            
        std::cout << "I will never lose deadline!" << std::endl;
        num--;                                                               
    }                                                
    
    return 0;
}  
EOF

```

Создаем коммит 

```sh
  ~/I-will-never-loose-deadline   main ?1 ❯ git add main.cpp          
  ~/I-will-never-loose-deadline   main +1 ❯ 
  ~/I-will-never-loose-deadline   main +1 ❯ git commit -m "added main.cpp"  
[main (корневой коммит) 23e5712] added main.cpp
 1 file changed, 13 insertions(+)
 create mode 100644 main.cpp
```

Далее пушим

```sh
  ~/I-will-never-loose-deadline   main ❯ git push origin main
Перечисление объектов: 3, готово.
Подсчет объектов: 100% (3/3), готово.
При сжатии изменений используется до 4 потоков
Сжатие объектов: 100% (2/2), готово.
Запись объектов: 100% (3/3), 366 байтов | 366.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To github.com:TheKamenski/I-will-never-loose-deadline.git
 * [new branch]      main -> main

```

Собираем проект с помощью Cmake:

```sh
  ~/I-will-never-loose-deadline   main ❯ cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.10)
project(main.cpp)

set(CMAKE_CXX_STANDARD 11)

add_executable(main.cpp main.cpp)
EOF
  ~/I-will-never-loose-deadline   main ?1 ❯ mkdir build               
  ~/I-will-never-loose-deadline   main ?1 ❯ cd build 
```
ИИИ...

```sh
  ~/I-will-never-loose-deadline/build   main ?1 ❯ cmake ..    
-- The C compiler identification is GNU 13.2.1
-- The CXX compiler identification is GNU 13.2.1
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done (0.3s)
-- Generating done (0.0s)
-- Build files have been written to: /home/konstantin/I-will-never-loose-deadline/build

```

###Готово запускаем:

```sh
[100%] Built target MyProgram
  ~/I-will-never-loose-deadline/build   main ?3 ❯ ./main.cpp
Enter a number: 3
I will never lose deadline!
I will never lose deadline!
I will never lose deadline!

``
