# Лабораторная работа №23. Интерактивные веб-приложения на JavaScript

**ФИО:** Шмаль Иван Максимович

**Группа:** ИСП-232

**Дата:** 24.03.2026

---

## Основная информация

### Цель работы:

>Закрепить и систематизировать знания по JavaScript путём разработки интерактивных веб-приложений с использованием HTML, CSS и JavaScript, а также закрепить навыки работы с системой контроля версий Git и удалёнными репозиториями GitHub.


### Краткая теория (вводная часть)

**JavaScript (JS)** — это интерпретируемый язык программирования, который изначально создавался для работы в браузере и управления поведением веб-страниц.

**Основные особенности JavaScript:**

- выполняется в браузере (frontend) и на сервере (Node.js);
- динамическая типизация;
- интерпретируемый язык (без компиляции в привычном смысле);
- активно работает с:
  - HTML;
  - CSS;
  - DOM.

- широко используется для:
  - интерактивных сайтов;
  - одностраничных приложений (SPA);
  - серверных API (Node.js).

---

## Структура проекта

- `index.html` — файл сайта
- `main.js` — запуск скрипта
- `README.md` — описание лабораторной работы
- `img/` — скриншоты

---

### Примеры:

```JS
const cells = document.querySelectorAll(".cell");
const statusText = document.getElementById("status");
const restartBtn = document.getElementById("restart");

let currentPlayer = "X"
let board = ["","","","","","","","",""];
let gameActive = true;

const winConditions = [
    [0,1,2],
    [3,4,5],
    [6,7,8],
    [0,3,6],
    [1,4,7],
    [2,5,8],
    [0,4,8],
    [2,4,6],
];

cells.forEach((cell) => {
    cell.addEventListener("click", handleCellClick);
});

restartBtn.addEventListener("click", restartGame);

function handleCellClick(event) {
    const cell = event.target;
    const index = cell.getAttribute("data-index");

    if (board[index] !== "" || !gameActive) {
        return;
    }

    board[index] = currentPlayer;
    cell.textContent = currentPlayer;

    checkResult();
}
```