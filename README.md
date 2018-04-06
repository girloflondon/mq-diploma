# Задание на дипломный проект курса «Адаптивная и мобильная верстка»

В рамках дипломного проекта вам необходимо сверстать макет сайта для трех групп устройств: десктопные экраны, планшеты и смартфоны.

Макеты сайта для различных экранов выглядят так:

![Layout](layouts.jpg)

Исходные файлы макетов хранятся в директории [sources](./sources/) репозитория:

- `surface_desktop.psd` – макет для экрана шириной 1920px,
- `surface_768.psd` – макет для экрана шириной 768px,
- `surface_320.psd` – макет для экрана шириной 320px.

О верстке промежуточных состояний подробнее читайте в разделе [Промежуточные состояния между макетами](#Промежуточные-состояния-между-макетами).

Также папка [sources](./sources/) содержит jpg-изображения – превью макетов для быстрого просмотра. **Не верстайте сайт с превью, используйте для верстки psd-макеты.**

В поддиректории [fonts](./sources/fonts/) вы можете найти использующиеся в макете шрифты, а в поддиректории [svg](./sources/svg/) — иконки в формате `svg`.

## Требования

#### Содержание
- [Кроссбраузерная верстка](#Кроссбраузерная-верстка)
- [Семантическое использование тегов](#Семантическое-использование-тегов)
- [Семантические названия атрибутов](#Семантические-названия-атрибутов)
- [Валидная верстка](#Валидная-верстка)
- [Соответствие верстки макету](#Соответствие-верстки-макету)
- [Реализация сетки](#Реализация-сетки)
- [Промежуточные состояния между макетами](#Промежуточные-состояния-между-макетами)
- [Добавление меньшего или большего количества контента в блоки](#Добавление-меньшего-или-большего-количества-контента-в-блоки)
- [Ошибки загрузки изображений](#Ошибки-загрузки-изображений)
- [Оформление кода](#Оформление-кода)
- [Файловая структура проекта](#Файловая-структура-проекта)
- [Публикация проекта](#Публикация-проекта)

### Кроссбраузерная верстка
В рамках проекта сверстанные макеты должны корректно отображаться на следующих типах устройств:
- компьютер с операционной системой Windows и Mac OS,
- планшеты и смартфоны с операционной системой iOS,
- планшеты и смартфоны с операционной системой Android.

Кроме поддержки основных типов устройств также требуется, чтобы верстка корректно работала в следующих браузерах:
- Последняя версия Google Chrome,
- Последняя версия Mozilla FireFox,
- IE 11,
- Последняя версия Edge,
- Последняя версия Opera,
- Последняя версия Safari,
- Последняя версия Mobile Safari,
- Последняя версия Mobile Chrome.

В случае, если у вас нет какого-то устройства, следует его найти. Тестирование на реальных устройствах является обязательным навыком современного специалиста.

### Семантическое использование тегов
В макетах проекта содержатся следующие элементы:
- Разделы,
- Заголовки,
- Ссылки,
- Изображения,
- Подписи,
- Абзацы.

Все эти элементы имеют специальные теги в стандарте HTML5, поэтому в рамках проекта вам необходимо их использовать.

К примеру, следующий код является грубой ошибкой:
```html
<div class="header">
  <div class="title">Заголовок сайта</div>
</div>
```

Кроме использования семантических тегов, также нужно правильно вкладывать теги по типу контекста. Запрещается в строчный элемент помещать блочный. Например, следующий код будет ошибочным:

```html
<span class="information">
  <h2 class="title">Заголовок блока</h2>
</span>
```

### Семантические названия атрибутов
Кроме использования семантических тегов также необходимо давать семантические названия значениям атрибутов. Запрещается использовать транслит. 

Пример:
```html
<header class="shapka"></header>
```
Данный пример является грубой ошибкой. Название класса `shapka` следует заменить на `header`. Пример корректного названия:
```html
<header class="header"></header>
```
### Валидная верстка
После полной реализации верстки необходимо ее протестировать с помощью сервиса [W3C Markup Validation Service](https://validator.w3.org). В итоговом отчете не должно быть ошибок или предупреждений.

### Соответствие верстки макету
Итоговый проект должен быть копией макетов, предоставленных дизайнером. При реализации допускаются следующие отличия:
- толщина шрифта в браузерах и фотошопе,
- межсимвольное расстояние,
- различия в отступах — до 2px.

### Реализация сетки
Реализовать сетку страницы вам нужно при помощи `flexbox`. Запрещено использовать библиотеки, которые уже имеют готовые классы для сетки (например, Twitter Bootstrap, Zurb Foundation и другие).

Также запрещено использовать следующие способы решения задачи:
- таблицы,
- float-сетка,
- сетка с помощью `inline-block` элементов,
- CSS Grids.

### Промежуточные состояния между макетами
Дизайнер подготовил три макета отображения страницы для устройств с шириной экрана 320px, 768px и 1920px. Но дизайнер не предоставил отображения страницы в промежуточных состояниях, поэтому их нужно реализовать с помощью принципа «Резиновая верстка».

Таким образом, на экранах с шириной больше 1920px фоновые блоки будут растягиваться на всю ширину экрана, а их контент будет центрироваться.

На устройствах с шириной экрана, попадающей в диапазон от 961px до 1920px, вам нужно реализовать дизайн макета `surface_desktop.psd`.

Для устройств с шириной экрана, попадающей в диапазон от 641px до 960px, вам нужно реализовать резиновый дизайн макета `surface_768.psd`.

Для устройств с шириной экрана, попадающей в диапазон от 640px и меньше, вам нужно реализовать резиновый дизайн макета `surface_320.psd`.

Для верстки изображений в промежуточных состояниях разрешается использовать изображения из макетов, более подходящие для данной ширины экрана. Например, блок «Be active» в макете `surface_desktop.psd` имеет ширину 960px, а в макете `surface_768.psd` — 768px. Соответственно, для экрана с шириной 960px больше подойдет версия из макета `surface_desktop.psd`.

### Добавление меньшего или большего количества контента в блоки
Вам обязательно нужно протестировать блоки с информацией, добавив в них больше или меньше контента, чем представлено в макетах. Блоки не должны сломать соседние блоки, текст при этом должен быть полностью читаемым.

### Ошибки загрузки изображений
При верстке изображений вам нужно предусмотреть ситуацию, когда по какой-либо причине они не загрузятся.

- В случае контентных изображений верстка не должна сломаться, а вместо изображения должен отображаться альтернативный текст, из которого станет понятно, что было изображено на картинке.

- Для декоративных изображений вам необходимо подобрать подложки для текста, чтобы текст был читаемым в любой ситуации. 

### Оформление кода
Дипломный проект обязательно должен соответствовать принятому стилю кода для [HTML](https://netology-university.bitbucket.io/codestyle/html/) и [CSS](https://netology-university.bitbucket.io/codestyle/css/). В случае ошибок в оформлении проект не может быть принят и будет отправлен на доработку. 

### Файловая структура проекта
Файловая структура проекта должна состоять из следующих элементов:
- `css` — папка, содержащая стили проекта,
- `fonts` — папка, содержащая шрифты проекта,
- `images` — папка, содержащая графику проекта,
- `index.html` — HTML-страница.

Файла проекта должны соответствовать [правилам именования файлов](https://netology-university.bitbucket.io/codestyle/naming/).  

### Публикация проекта

При разработке проекта и для итоговой демонстрации вам нужно использовать сервис GitHub Pages. Перед работой с сервисом ознакомьтесь с [пошаговой инструкцией](https://netology-university.bitbucket.io/guides/github-pages/index.html).
