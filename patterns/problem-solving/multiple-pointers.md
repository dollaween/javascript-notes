<div align="center">

# Multiple Pointers

[Вопросы](https://github.com/dollaween/javascript-questions)
|
[Тесты](https://github.com/dollaween/javascript-tests)
|
[Задачи](https://github.com/dollaween/javascript-tasks)
|
[Заметки](https://github.com/dollaween/javascript-notes)

</div>

---

**Multiple Pointers** — это паттерн, при котором создаются несколько указателей, соответствующих индексу или позиции, и двигающихся по направлению к началу/концу/середине от начальной позиции. Паттерн крайне эффективен для решения задач с минимальной простраственной сложностью (space complexity).

Подходит для:
* Сравнивания/использования значений массива начиная одновременно из начала и конца
* Слияния двух отсортированных массивов в один отсортированный

#### Реализация 1
1. При необходимости, отсортируйте массив
2. Создайте два указателя: на индексы 0 и 1.
3. Пройдитесь по массиву до конца, в каждой итерации передвигая индексы на +1.

```js
/**
 * Напишите функцию, которая принимает неограниченное количество аргументов
 * и возвращает false, если среди аргументов нет повторяющихся.
 */
function areThereDuplicates(...args) {
  args = args.sort()

  let a = 0
  let b = 1

  for (; b < args.length; a++, b++) {
    if (args[a] === args[b]) {
      return true
    }
  }

  return false
}

areThereDuplicates(1, 2, 3)     // false
areThereDuplicates(1, 2, 3, 1)  // true
```

#### Реализация 2
1. При необходимости, отсортируйте массив
2. Создайте два указателя: на индексы 0 и length - 1.
3. Итерируйте массив увеличивая первый курсор на +1, а второй на -1 до тех пор, пока первый указатель не будет больше второго.

```js
/**
 * Напишите функцию, которая проверяет, что элементы в массиве `arr1`
 * содержатся в массиве `arr2` в том же порядке, но реверсивно
 */
function isItReverseArray(arr1, arr2) {
  if (arr1.length !== arr2.length) return false

  let a = 0
  let b = arr2.length - 1

  for (; a < arr1.length; a++, b--) {
    if (arr1[a] !== arr2[b]) {
      return false
    }
  }

  return true
}

isItReverseArray([1, 2, 3, 4], [4, 3, 2, 1])
// true
```

Иллюстрация:
```js
// a                 b
// 1 2 3 4  |  4 3 2 1
//
//   a             b
// 1 2 3 4  |  4 3 2 1
//
//     a         b
// 1 2 3 4  |  4 3 2 1
//
//       a     b
// 1 2 3 4  |  4 3 2 1
```
