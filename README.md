# Bose - Lesson 3 — Основний вміст сторінки

У цьому уроці ми завершуємо з меню та починаємо стилізувати «начинку» нашої сторінки.

## Відкриваємо меню по кліку

Тепер зробімо, щоб меню з'являлося по кліку. Для цього:

1. Покажи `header`, видаливши `display: none;` та розкоментувавши `display: flex;` (натисни `ctrl/cmd` та `/`).
2. Обгорни іконку меню в посилання з `href="#menu"`.
3. Блоку menu додай `id="menu"`.
4. Встанови для `.menu` властивість `position: fixed;` та `top: 0;`, щоб прив'язати його до верху сторінки.
5. Розтягни меню горизонтально за допомогою `left: 0;` та `right: 0;`.
6. Зсунь `.menu` ліворуч за край екрана:
```css
  `transform: translateX(-100%);`
```

7. Далі, щоб меню з'являлося коли адреса завершується на `#menu`, додай таке правило:
```css
.menu:target {
  transform: translateX(0);
}
```
Тепер меню з'являється при кліку на іконці. Щоб його закрити, так само обгорни `x` у посилання на `#home` [#home](посилання-сюди). А щоб відкриття було плавним, додай наступне правило до `.menu`:

```css
transition: transform 500ms;
```
## Стилізуємо заголовки

Додай до заголовка секції `Recommended` клас `recommended__title` та використай наступні скорочення і `tab`, щоб додати необхідні стилі для нього:

- `fz48` -> `font-size: 48px;`
- `lh100%` -> `line-height: 100%;`
- `fwb` -> `font-weight: bold;`
- `tac` -> `text-align: center;`
- `ls-1` -> `letter-spacing: -1px;` тільки зміни на `-1.5px`

А `color: #292929;` варто одразу записати для `body`, щоб встановити цей колір для всіх текстів.

## Відступи

Щоб побачити поточні відступи елемента `.recommended__title`, натисни на ньому правою клавішею та обери `Inspect`. Унизу в панелі праворуч обери вкладку `Computed`. Там ти побачиш поточні `margin`, `border` та `padding`, якщо вони є.

Щоб встановити правильні відступи:

1. Додай клас для `main` та внутрішні відступи для нього (`p120 -> padding: 120px;`).
2. Для `.recommended__title` скинь верхній відступ (`mt0 -> margin-top: 0;`).
3. Та задай нижній `mb64 -> margin-bottom: 64px;`.

## Виправляємо стилі основного заголовка

Зараз другий заголовок став більше основного. Виправ це:

1. Додай клас `header__title` для `h1`.
2. Скопіюй правила для `.header__title` з `.recommended__title`:
```css
margin-top: 0;
margin-bottom: 64px;
font-size: 48px;
line-height: 100%;
font-weight: bold;
text-align: center;
letter-spacing: -1.5px;
```

3. Верхній відступ має бути `40px`.
4. Нижній відступ має бути `0`.
5. Замість `text-align: center;` зроби шрифт курсивним `font-style: italic;`.
6. Зміни `font-weight` на `800`.
Щоб товщина `800` застосувалася, її треба додати для шрифту `Inter`. Тож допиши `;800` то тегу `<link>` зі шрифтом або просто заміни його на наступний:
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;800&display=swap" rel="stylesheet">
```

## Заголовки інших секцій

Тепер для заголовка секції `categories` додай клас `categories__title` та скопіюй усі стилі з `.recommended__title`.

Так само і для `how-to-buy__title`, тільки без центрування.

## Заповнюємо секцію Recommended

Крім заголовка тут буде 3 товари розміщені в ряд, тож зроби наступне:

1. Збережи зображення товарів у папку `images/products`, використовуючи назви товарів як імена файлів.
2. Додай тег `<article>` з класом `product` для першого товару.
3. Усередині буде зображення з класом `product__photo` і назвою в атрибуті `alt` (кожен атрибут варто писати на окремому рядку).
4. Заголовок `## Заголовок із класом product__title і назвою`.
5. Параграф `Параграф із класом product__category і текстом із макета`.
6. Та параграф із класом product__price та ціною.

Додай аналогічні теги й для інших двох товарів.

Для розміщення в ряд, обгорни 3 товари в `div` із класом `recommended__products` і додай наступні стилі:

```css
.recommended__products {
  display: flex; /* fd */
  gap: 24px; /* gap24 */
  justify-content: center; /* jcc */
  width: 100%; /* w100% */
}

.product__photo {
  width: 100%; /* w100% */
}

.product {
  flex-basis: 324px;
}
```

```css
/* Flexbox styles */
`fd` -> `display: flex;`
`gap24` -> `gap: 24px;`
`jcc` -> `justify-content: center;`
`w100%` -> `width: 100%;`
`flex-basis` -> `flex-basis: 324px;`

/* Margins and padding */
`.recommended` -> `margin-bottom: 120px;`
`.product__photo` -> `margin-bottom: 32px;`
`.product__title` -> `margin-top: 0; margin-bottom: 8px;`
`.product__category` -> `margin-top: 0; margin-bottom: 12px;`
`.product__price` -> `margin: 0;`

/* Text styles */
`body` -> `font-size: 16px; line-height: 140%;`
`.product__title` -> `font-size: 16px;`
`.product__price` -> `font-weight: bold;`

/* Centering */
To center items on wide screens, use appropriate CSS rules.
```

`fd` -> `display: flex;`
`gap24` -> `gap: 24px;`
Відцентруй картки за допомогою `jcc` -> `justify-content: center;`.
Задай ширину `w100%` -> `width: 100%;` для зображень `.product__photo`, щоб вони вмістилися на сторінці.
А щоб ширина товарів була однаковою, для `.product` треба встановити `flex-basis: 324px;` (це розмір із макета).
Тепер додай відступи:

Для `.recommended` робимо відступ знизу `mb120` -> `margin-bottom: 120px;`.
Для `.product__photo` робимо `mb32`.
Для `.product__title` робимо `mt0` та `mb8`.
Для `.product__category` робимо `mt0` та `mb12`.
А для `.product__price` скидаємо відступи `m0` -> `margin: 0`.
Для текстів зроби наступне:

Для `body` встанови `fz16` та `lh140%`, це будуть стандартні розміри.
Для `.product__title` задай `fz16`.
А для `.product__price` тільки `fwb` -> `font-weight: bold`.
Тепер товари мають виглядати як у макеті та бути по центру на широкому екрані.

## Фінальний код уроку
Зверни увагу: ми додали цей фінальний код із метою підказки. Але перш ніж туди підглянути, спробуй написати код із відео самостійно 😉

- *default.html*
- *default.css*
