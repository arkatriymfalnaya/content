Чтобы понять что такое progressive rendering, нужно понимать отличие _clisent-side rendering_ от _server-side rendering_.

При **clisent-side rendering** (CSR) контент отрисовывается на стороне клиента (в браузере). Такой подход используется в React, когда браузеру отсылается практически пустой HTML-документ, а потом запускается скрипт, который генерирует HTML в указанном скрипту теге. Как правило это `<div id="root">`. Пользователь будет видеть пустую страницу, пока JS-файл полностью не загрузится.

При **server-side rendering**  (SSR) HTML-разметка генерируется на сервере, отсылается браузеру и после этого отрисовывается на клиенте. Пользователь увидит контент сразу же, но не сможет взаимодействовать со страницей, пока не загрузится JS-файл.

При использовании прогрессивного рендеринга, кусочки HTML генерируется на сервере и отсылаются браузеру в порядке их приоритетности. То есть, элементы с самым высоким приоритетом (например `<header>`, фон, главная интерактивная часть страницы) генерируются на сервере, отсылаются браузеру и отрисовываются в первую очередь. Это позволяет пользователю увидеть самый важный контент как можно скорее, не дожидаясь полной загрузки всего контента. То есть, progressive rendering что-то среднее между clisent-side rendering и server-side rendering.

Техники реализации прогрессивного рендеринга:

1. **Ленивая загрузка** (Lazy Loading). Загрузка контента по мере необходимости. Например, если страница достаточно большая, не нужно загружать изображения вне вьюпорта. Загрузка изображения стартует за некоторое время до того как она появится во вьюпорте. Эту же технику можно использовать для загрузки контента изначально скрытых элементов. Например, можно загрузить контент закрытого меню когда пользователь наводит курсор на кнопку открытия.
1. **Приоритизация контента**. Например, не загружать изначально все CSS-стили. Добавлять в `<head>` загрузку только тех стилей, которые нужны для текущей видимой области HTML-документа. Остальные стили можно добавить в `<body>`.