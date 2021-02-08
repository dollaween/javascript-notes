<div align="center">

# Sliding Window

[Вопросы](https://github.com/dollaween/javascript-questions)
|
[Тесты](https://github.com/dollaween/javascript-tests)
|
[Задачи](https://github.com/dollaween/javascript-tasks)
|
[Заметки](https://github.com/dollaween/javascript-notes)

</div>

---

Подходит для:
* Поиска диапазона и последовательности в массиве/строке

#### Реализация 1
1. Найдите изначальный подмассив.
2. В каждой новой итерации добавляйте элемент в конец и удаляйте элемент в начале.
3. Произведите перерасчет, сравнив новый расчет с предыдущим.

```js
/**
 * Напишите функцию, которая принимает неограниченное количество аргументов
 * и возвращает false, если среди аргументов нет повторяющихся.
 */
function maxSubarraySum(nums, n) {
  if (nums.length < n) {
    return null
  }

  let max = 0
  let temp = 0

  // Задаем изначальное окно, которое будем двигать
  for (let i = 0; i < n; i++) {
    max += nums[i]
  }

  temp = max;
  for (let i = n; i < nums.length; i++) {
    // Производим перерасчет
    temp = temp - nums[i - n] + nums[i]
    // Сравниваем новый расчет с предыдущим
    max = Math.max(max, temp)
  }

  return max
}
```
