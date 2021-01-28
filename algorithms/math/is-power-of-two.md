<div align="center">

# Степень двойки

[Вопросы](https://github.com/dollaween/javascript-questions)
|
[Тесты](https://github.com/dollaween/javascript-tests)
|
[Задачи](https://github.com/dollaween/javascript-tasks)
|
[Заметки](https://github.com/dollaween/javascript-notes)

</div>

---

Дано позитивное целое число, напишите функцию, которая определит является ли это число степенью двойки или нет.

#### Наивное решение
В наивном решение мы продолжаем делить на два до тех пор, пока число не станет равным `1` и при этом в каждой итерации мы проверяем, чтобы остаток от деления был равен `0`. В противном случае число не может быть степенью двойки.

#### Побитовое решение

```js
function isPowerOfTwoBitwise(number) {
  if (number < 1) {
    return false
  }

  return (number & (number - 1)) === 0
}
```
