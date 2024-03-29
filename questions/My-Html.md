<h3>
  <img src="../assets/HTML.png" width="16" height="16" />
  <span>HTML:</span>
</h3>

1. - Вопрос [Зачем нужна деректива doctype в блоке HTML документа?]()

   - Ответ [Doctype (Document Type Declaration или DTD) — это часть html-кода страницы, “инструкция”, которая объявляет тип документа и объясняет браузеру, в какой версии языка разметки он сверстан. Doctype должен указываться в самом верху документа перед тегом <html> .]()

2. - Вопрос [Опишите базовую структуру HTML-страницы?]()

   - Ответ [Базовая структура HTML-страницы состоит из следующих основных элементов:

   1. `<!DOCTYPE>` (объявление типа документа): Это объявление указывает браузеру на используемую версию HTML. Например, для HTML5 это объявление выглядит так:

   ```html
   <!DOCTYPE html>
   ```

   2. `<html>` (корневой элемент HTML): Этот элемент определяет начало и конец HTML-документа. Все содержимое документа должно быть вложено внутрь этого элемента.
   3. `<head>` (заголовок документа): Внутри этого элемента обычно содержится метаинформация о странице, такая как заголовок документа, ссылки на внешние ресурсы (стили, скрипты), мета-теги и другие настройки.
   4. `<meta>` (метаинформация): Элемент `<meta>` используется для определения метаданных о документе, таких как кодировка символов, описание, ключевые слова и другие важные сведения для поисковых систем и браузеров.
   5. `<title>` (заголовок документа): Этот элемент содержит заголовок страницы, который отображается в верхней части браузера и часто используется в закладках (вкладках) браузера.
   6. `<body>` (тело документа): Этот элемент содержит основное содержимое HTML-страницы, такое как текст, изображения, ссылки, таблицы и другие элементы, которые отображаются на веб-странице и взаимодействуют с пользователем.
      Пример базовой структуры HTML-страницы:

   ```html
   <!DOCTYPE html>
   <html>
     <head>
       <meta charset="UTF-8" />
       <meta name="description" content="Описание вашей веб-страницы" />
       <meta name="keywords" content="ключевые слова, для, поиска" />
       <title>Заголовок вашей страницы</title>
     </head>
     <body>
       <h1>Привет, мир!</h1>
       <p>Это пример базовой HTML-страницы.</p>
     </body>
   </html>
   ```

   Это минимальная структура HTML-страницы, которая может быть дополнена другими элементами и атрибутами в зависимости от требований и содержания вашей веб-страницы.]()

3. - Вопрос [Для чего нужны meta тэги?]()

   - Ответ [-Мета-теги – это специальные элементы кода, через которые браузер и поисковые машины считывают информацию о сайте. Эти атрибуты не видны пользователям, но считаются очень важными для корректной работы ресурса. Теги просто описывают веб-страницу с помощью заголовка, дескриптора, ключевых фраз.]()

4. - Вопрос [Что описывается в тэге `<head>`]()

   - Ответ [Элемент `<head>` в HTML-документе содержит метаинформацию о странице, которая не отображается напрямую на самой странице, но важна для её корректной обработки и отображения в браузере. Вот основные элементы, которые обычно размещаются внутри тега `<head>`]()

   1. `<title>`: Этот элемент определяет заголовок страницы, который отображается в верхней части браузера, во вкладке и используется при добавлении страницы в избранное. Пример:

   ```html
   <title>Заголовок вашей страницы</title>
   ```

   2. `<meta>`: Элемент `<meta>` используется для указания метаданных о странице. Например, можно задать кодировку символов, описание страницы для поисковых систем, ключевые слова и другие важные сведения. Примеры:

   ```html
   <meta charset="UTF-8" />
   <!-- Задание кодировки символов -->
   <meta name="description" content="Описание вашей веб-страницы" />
   <meta name="keywords" content="ключевые слова, для, поиска" />
   ```

   3. Ссылки на внешние ресурсы: Элементы `<link>` и `<script>` используются для подключения внешних файлов стилей (CSS) и скриптов JavaScript соответственно. Примеры:

   ```html
   <link rel="stylesheet" type="text/css" href="styles.css" />
   <!-- Подключение CSS-стилей -->
   <script src="script.js"></script>
   <!-- Подключение JavaScript-скрипта -->
   ```

   4. Другие метаинструкции: В `<head>` могут быть включены и другие элементы, такие как инструкции для социальных сетей (например, для предварительного просмотра ссылки на страницу в Facebook или Twitter).

   5. Ссылки на иконки: Для задания иконки (favicon), которая отображается во вкладке браузера, используется элемент `<link>` с атрибутом `rel="icon"`. Пример:

   ```html
   <link rel="icon" type="image/png" href="favicon.png" />
   ```

   6. Другие элементы, такие как `<base>` (задание базового URL) и `<style>` (внутренние стили).

   Элемент `<head>` не содержит видимого контента для пользователя, но его содержимое оказывает важное воздействие на процесс обработки и отображения веб-страницы браузером, поисковыми системами и другими инструментами. ]()

5. - Вопрос [Опишите подробно базовую структуру в реальном проекте HTML-страницы]()

   - Ответ [Этот код представляет собой базовый HTML-документ, который определяет структуру и содержимое веб-страницы. Давайте рассмотрим каждый элемент более подробно:

   1. `<!DOCTYPE html>`:

   - Это объявление типа документа (Document Type Declaration), которое сообщает браузеру, какую версию HTML следует ожидать. В данном случае, это `html`, что указывает на HTML5.

   2. `<html lang="en">`:

   - Этот элемент обозначает начало HTML-документа. Атрибут `lang="en"` указывает язык содержимого, в данном случае, английский. Этот атрибут полезен для доступности и поисковых систем.

   3. `<head>`:

   - Этот элемент содержит метаинформацию о документе, такую как мета-теги, заголовок страницы и подключение стилей. В данном случае, он содержит:
     - `<meta charset="UTF-8" />`: Устанавливает кодировку символов документа на UTF-8, что поддерживает большинство символов в различных языках.
     - `<meta name="viewport" content="width=device-width, initial-scale=1.0" />`: Определяет параметры отображения страницы на мобильных устройствах, такие как ширина экрана и начальный масштаб.
     - `<title>Victory Proxy</title>`: Устанавливает заголовок страницы, который отображается в заголовке веб-браузера.

   4. `<body>`:

   - Этот элемент содержит основное содержимое страницы. В данном случае, он включает в себя:
     - `<div id="root"></div>`: Пустой `div` с идентификатором "root". Это место, где, вероятно, будет отрисовываться контент вашего веб-приложения с использованием JavaScript или фреймворков, таких как React.
     - `<script type="module" src="/src/main.tsx"></script>`: Подключает внешний скрипт, написанный на TypeScript и расположенный по пути "/src/main.tsx". Модульный тип (`type="module"`) говорит браузеру, что это модульный скрипт, который может использовать инструкции `import` и `export`.

   Этот HTML-документ предоставляет основную структуру для веб-приложения и загружает главный скрипт для дальнейшей обработки и отображения контента.]()

6. - Вопрос [Meta тег viewport для чего он нужен?]()

   - Ответ [-Метатег Viewport используется для адаптации сайта ко всем устройствам и задает правила отображения видимой области в мобильном браузере. Чтобы активировать тег, необходимо добавить его в раздел Head кода страницы, задав нужные параметры. Viewport — это область, которую видит пользователь на экране, когда заходит на страницу сайта с любого устройства.Meta-тег viewport сообщает браузеру о том, как именно обрабатывать размеры страницы, и изменять её масштаб.Универсальное решение: `<meta name="viewport" content="width=device-width, initial-scale=1.0">.`]()

7. - Вопрос [Для чего используется тэг `iFrame`]()

   - Ответ [Тег iFrame — элемент HTML, позволяющий встраивать на веб-страницу документы, видео и интерактивные медиафайлы и прочие части содержимого из других источников. Это один из старейших HTML-элементов: впервые его поддержка была включена в браузер Microsoft Internet Explorer в 1997 году.упрощает хранение мультимедийных файлов: вместо того чтобы создавать видеоплеер с нуля и размещать видеоматериалы на собственном хостинге, можно загрузить все ролики на YouTube-канал и добавить их на страницу с помощью фреймов.

   Пример использования іFrame  
   Встроить страницу с другого сайта очень просто:

   `<iframe src='https://skillfactory.ru/' height=»500px» width=»500px»></iframe>`]()

8. - Вопрос [Какая разница между тэгами `div` и `span`]()

   - Ответ [Теги `<div>` и `<span>` являются блочными и строчными элементами соответственно, и их использование зависит от целей структурирования контента на веб-странице.

   1. `<div>` (блочный элемент):

   - `<div>` представляет собой блочный элемент, который обычно используется для группировки других элементов и создания блочных контейнеров.
   - Этот тег обычно применяется, когда вам нужно создать блок на странице, который может содержать другие блочные и строчные элементы.
   - Пример использования:
     ```html
     <div>
       <p>Это абзац внутри блока.</p>
       <ul>
         <li>Элемент списка 1</li>
         <li>Элемент списка 2</li>
       </ul>
     </div>
     ```

   2. `<span>` (строчный элемент):

   - `<span>` является строчным элементом т.е.("занимает только всю ширину содержимого") и обычно используется для применения стилей или обработки текстового содержимого внутри других элементов, таких как параграфы или заголовки.
   - Этот тег обычно применяется, когда вам нужно применить стили, скрипты или другие свойства к части текста внутри строчного контейнера.
   - Пример использования:
     ```html
     <p>Это <span style="color: blue;">строчный текст</span> внутри абзаца.</p>
     ```

   В общем, разница между `<div>` и `<span>` заключается в их типе (блочный или строчный) и том, как они обычно применяются. `<div>` используется для создания блочных контейнеров и группировки элементов, в то время как `<span>` используется для работы с отдельными частями текста внутри других элементов.]()

9. Вопрос [Какая разница между тэгами `<strong> <em>` и `<b> <i>`]()

   - Ответ [Тэги `<strong><em>` и `<b><i>` в HTML используются для придания тексту выделения и форматирования, но имеют разные семантические значения и рекомендации к использованию.

   1. `<strong>` и `<em>`:

   - `<strong>` используется для придания тексту семантической важности и выделения его как важного, весомого. Это может быть использовано для выделения ключевых слов, фраз, заголовков и т. д. Это также может помочь программам чтения экрана и поисковым системам понимать, что текст является более важным.
   - `<em>` используется для выделения текста как ударения, акцента или уточнения. Он придает тексту курсивное начертание и подчеркивает его важность с точки зрения акцента, но не обязательно с точки зрения семантической важности. Это может использоваться, например, для выделения чужих слов, терминов, цитат и т. д.

   Пример использования:

   ```html
   <p><strong>Важный текст</strong> и <em>акцентированный текст</em></p>
   ```

   2. `<b>` и `<i>`:

   - `<b>` используется для придания тексту полужирного начертания, но не имеет семантического значения. Он просто делает текст жирным и может использоваться для стилизации текста.
   - `<i>` используется для придания тексту курсивного начертания, но также не имеет семантического значения. Он используется для стилизации текста, но не изменяет его смысла.

   Пример использования:

   ```html
   <p><b>Жирный текст</b> и <i>курсивный текст</i></p>
   ```

   Рекомендуется использовать тэги `<strong>` и `<em>` в первую очередь, если у вас есть семантическая основа для выделения текста, чтобы улучшить доступность и семантику вашей веб-страницы. Тэги `<b>` и `<i>` следует использовать только для стилизации текста без изменения его смысла, например, если вы хотите создать определенный визуальный эффект.]()

10. Вопрос [Для какого тэга используется атрибут `alt` и зачем он нужен?]()

    - Ответ [Атрибут `alt` используется в HTML для тега `<img>` (тега изображения) и предназначен для предоставления альтернативного текста для изображения. Этот атрибут играет важную роль с точки зрения доступности и SEO, и его основные цели следующие:

    1. **Доступность (Accessibility)**: Атрибут `alt` предоставляет текстовое описание изображения для пользователей с ограниченными возможностями, такими как пользователи программ чтения экрана. Когда программа чтения экрана обнаруживает изображение с атрибутом `alt`, она может прочитать этот текст пользователю, что позволяет им понимать, что изображено на экране. Это особенно важно для пользователей, которые не могут видеть изображения, например, слепых или слабовидящих людей.

    2. **Поисковая оптимизация (SEO)**: Атрибут `alt` также используется поисковыми системами для определения содержания изображения. Это позволяет улучшить SEO вашей веб-страницы, поскольку поисковые системы могут индексировать и анализировать содержание изображений с атрибутами `alt`. Хорошо подобранный и описательный текст в атрибуте `alt` может помочь в повышении видимости вашего контента в поисковых результатах.

    Пример использования атрибута `alt`:

    ```html
    <img src="example.jpg" alt="Красивый закат на озере" />
    ```

    В данном примере, значение атрибута `alt` ("Красивый закат на озере") предоставляет краткое описание содержания изображения "example.jpg". Этот текст будет отображаться вместо изображения, если оно не загружено или если пользователь использует программу чтения экрана.

    Важно использовать атрибут `alt` соответственно и точно описывать содержание изображения, чтобы обеспечить лучшую доступность и оптимизацию для поисковых систем.]()
