<div align="center">

# Typescript

[Вопросы](https://github.com/dollaween/javascript-questions)
|
[Тесты](https://github.com/dollaween/javascript-tests)
|
[Задачи](https://github.com/dollaween/javascript-tasks)
|
[Заметки](https://github.com/dollaween/javascript-notes)

</div>

---

<div align="center">

  ### Примитивы

</div>

---

```ts
type Props = {
  name: string;       // John
  age: number;        // 33
  hasBeard: boolean;  // false
}
```

---

<div align="center">

  ### Массивы

</div>

---

```ts
type Props = {
  nums: number[];    // [1, 2, 3]
  strs: string[];    // ['hello', 'world']
  bools: boolean[];  // [true, true, false]
}
```

---

<div align="center">

  ### Функции

</div>

---

Типизация параметров и возвращаемого результата.

```ts
function greet(name: string): string {
  return name;
}
```

```ts
function coordinate(obj: { x: number; y: number }) {}
```

---

<div align="center">

  ### Автоматическое типизирование

</div>

---

Для переменных объявленных через `const`, `let`, или `var` типизация будет вычислена автоматически, ее можно не добавлять.

```ts
let myName: string = "Alice";

// Типизацию можно не добавлять
let myName = "Alice";
```

Возвращаемое значение в функциях так же вычисляется автоматически.

```ts
function getNum(): number {
  return 32;
}

// Типизацию можно не добавлять
function getNum() {
  return 32;
}
```

#### Контекстное типизирование

```ts
// Автоматическое типизирование
const names = ["Alice", "Bob", "Eve"];
 
// Контекстное типизирование на основе типа names
names.forEach((s) => {
  console.log(s.toUpperCase());
});
```

---

<div align="center">

  ### Необязательные параметры

</div>

---

Чтобы указать что поле необязательное — после его названия ставим знак вопроса.  
В таком случае, в коде нужно будет дополнительно проверять поле на существование.

```ts
function printName(obj: { first: string; last?: string }) {
  if (obj.last) {
    console.log(obj.last.toUpperCase())
  }
}
```

---

<div align="center">

  ### Объединение типов

</div>

---

У одного параметра может быть несколько типов.  
При использовании параметра с несколькими типами, нужно создавать доп. проверки.

```ts
function printId(id: number | string) {
  if (typeof id === 'string) {
  } else {}
}
```
















