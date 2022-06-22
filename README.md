# Stream-API1
# Задача 1: Работа с числами

## Описание
Работа с коллекциями является обычной задачей в программировании. Такие операции как сортировка, фильтрация, перебор встречаются в каждом проекте. Работа с коллекциями в Java значительно упростилась с появлением `Stream API`. Давайте сравним два подхода! 

Составьте ArrayList из набора чисел `1, 2, 5, 16, -1, -2, 0, 32, 3, 5, 8, 23, 4` и произведите над ним следующие действия:
1. Отфильтруйте положительные числа.
2. Найдите среди этих положительных чисел четные.
3. Отсортируйте отфильтрованные числа в порядке возрастания.
4. Выведите результат на экран.

## Реализация
Реализуйте два класса `Main` и `StreamMain`, в каждом из которых в функции `main()` составьте ArrayList из приведенных выше чисел и произведите над ними указанные операции, причем:
* в первом классе выполнените работу без использования `Collection API` и `Stream API`;
* во втором классе используйте стримы из библиотеки `Stream API`.

Получить ArrayList из чисел можно следующим образом:
```java
List<Integer> intList = Arrays.asList(1, 2, 5, 16, -1, -2, 0, 32, 3, 5, 8, 23, 4);
```
Для получения потока из массива целых чисел используйте:
```java
Stream<Integer> stream = intList.stream();
```
К потоку примените ряд промежуточных операций:
```java
filter(x -> x > 0)
filter(x -> x % 2 == 0)
sorted(Comparator.naturalOrder())
```
Потребуется и терминальная операция. Например:
```java
forEach(System.out::println)
```
И с помощью стримов, и без них Вы должны получить одинаковый ответ:
2
4
8
16
32

