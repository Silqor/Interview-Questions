<h3>
  <img src="../assets/WWW.png" width="16" height="16" />
  <span>Web API:</span>
</h3>

- [Что такое `HTTP`?](https://youtu.be/w-vUj0gHGgg?t=422)
- Вопрос [Разница между cookies storage(данные хранят определенный период времени), local storage(пока находимся), session storage(браузер)?]()

      - Ответ[`Cookies`, `localStorage` и `sessionStorage` - это различные механизмы хранения данных в веб-браузерах, но у них есть существенные различия в том, как данные хранятся и доступны.

  1. **Cookies (Куки):**

     - `Cookies` - это небольшие текстовые файлы, которые веб-сервер отправляет и хранит в браузере пользователя. Они могут содержать небольшие объемы данных и обычно используются для отслеживания состояния сеанса, аутентификации и предпочтений пользователя.
     - `Cookies` сохраняются на долгий срок, указанный при создании (`expires` или `max-age`), и могут быть доступны между сеансами браузера.

     ```javascript
     // Создание куки
     document.cookie =
       'username=John Doe; expires=Thu, 18 Dec 2023 12:00:00 UTC; path=/';
     ```

  2. **localStorage:**

     - `localStorage` - это объект для хранения пар ключ-значение в локальном хранилище браузера. Данные в `localStorage` сохраняются на долгий срок и будут доступны после перезапуска браузера.
     - Данные в `localStorage` не имеют срока действия и сохраняются даже после закрытия браузера и перезапуска компьютера.

     ```javascript
     // Сохранение в localStorage
     localStorage.setItem('username', 'John Doe');

     // Получение из localStorage
     const username = localStorage.getItem('username');
     ```

  3. **sessionStorage:**

     - `sessionStorage` - это объект для хранения данных в сеансе браузера. Данные в `sessionStorage` доступны только в течение одной сессии браузера и удаляются, когда закрывается вкладка или окно браузера.
     - Данные в `sessionStorage` не сохраняются после перезапуска браузера.

     ```javascript
     // Сохранение в sessionStorage
     sessionStorage.setItem('username', 'John Doe');

     // Получение из sessionStorage
     const username = sessionStorage.getItem('username');
     ```

  Выбор между `cookies`, `localStorage` и `sessionStorage` зависит от требований вашего приложения. Если вам нужно сохранить данные на долгий срок и сделать их доступными между сеансами браузера, используйте `cookies` или `localStorage`. Если данные должны быть доступны только в течение одной сессии, используйте `sessionStorage`.

  **Какие данные хранятся в каждом из них?**
  Данные, которые могут быть хранены в `cookies`, `localStorage` и `sessionStorage`, могут включать в себя различные типы информации, и каждый из этих механизмов предназначен для различных целей. Вот несколько типичных сценариев использования и типов данных для каждого из них:

  1. **Cookies:**

     - `Cookies` часто используются для следующих целей:
       - Аутентификация пользователя: хранение данных для идентификации пользователя.
       - Слежение за сеансом: отслеживание активности пользователя на веб-сайте.
       - Хранение предпочтений пользователя: сохранение настроек и предпочтений.
     - Данные, которые могут быть хранены в `Cookies`:
       - Идентификатор сеанса (session ID).
       - Токен аутентификации.
       - Информация о предпочтениях пользователя.
       - Другие краткосрочные данные.

  2. **localStorage:**

     - `localStorage` предназначен для долгосрочного хранения данных между сеансами браузера.
     - Данные, которые могут быть хранены в `localStorage`:
       - Настройки приложения.
       - Пользовательские предпочтения.
       - Сведения о последних посещениях пользователя.
       - Локальные данные, которые необходимо сохранить между сеансами.

  3. **sessionStorage:**

     - `sessionStorage` предназначен для хранения данных в течение одной сессии браузера (до закрытия вкладки или окна браузера).
     - Данные, которые могут быть хранены в `sessionStorage`:
       - Временные данные для текущего сеанса.
       - Состояние текущей сессии пользователя.
       - Данные, которые могут быть безопасно удалены после закрытия вкладки.

  Примеры кода для сохранения и получения данных:

  ```javascript
  // Cookies
  document.cookie =
    'username=John Doe; expires=Thu, 18 Dec 2023 12:00:00 UTC; path=/';
  const cookieValue = document.cookie;

  // localStorage
  localStorage.setItem('username', 'John Doe');
  const localStorageValue = localStorage.getItem('username');

  // sessionStorage
  sessionStorage.setItem('username', 'John Doe');
  const sessionStorageValue = sessionStorage.getItem('username');
  ```

  Обратите внимание, что хранение конфиденциальной или чувствительной информации в `cookies`, `localStorage` или `sessionStorage` может представлять риски безопасности, и поэтому важно следить за безопасностью хранения данных, особенно в случае `cookies`.

  **Где хранится токен?**
  Токен обычно хранится в различных местах в зависимости от сценария использования и требований безопасности. Вот несколько распространенных мест хранения токенов:

  1. **Cookies:**

     - Токен может быть сохранен в виде `httpOnly` cookie, что означает, что его можно использовать только сервером и не доступно JavaScript в браузере. Это повышает уровень безопасности, так как токен не может быть украден с использованием атак XSS (межсайтового сценария).

  2. **LocalStorage и SessionStorage:**

     - Токены могут быть хранены в `localStorage` или `sessionStorage` браузера. Однако следует быть осторожным с использованием `localStorage`, так как данные в нем доступны JavaScript, и, следовательно, могут быть подвержены атакам XSS. В то время как `sessionStorage` ограничивается текущей сессией и закрывается при закрытии вкладки.

       ```javascript
       // Пример сохранения токена в localStorage
       localStorage.setItem('accessToken', 'your_token_here');

       // Пример сохранения токена в sessionStorage
       sessionStorage.setItem('accessToken', 'your_token_here');
       ```

  3. **HTTP-заголовки:**

     - Токены могут быть переданы в заголовках HTTP-запроса, например, в заголовке `Authorization`. Этот метод часто используется при аутентификации с использованием токенов Bearer.

       ```javascript
       // Пример передачи токена в заголовке запроса
       const headers = {
         Authorization: `Bearer your_token_here`,
       };
       ```

  4. **Конечная точка запроса (Query Parameter):**

     - Токен может быть передан как параметр в URL запроса. Это менее безопасный метод, так как токен может быть виден в строке запроса и сохранен в журналах сервера.

       ```javascript
       // Пример передачи токена в URL запроса
       const url = 'https://example.com/api/data?access_token=your_token_here';
       ```

  Выбор места хранения токена зависит от требований безопасности и конкретных сценариев использования приложения. Когда речь идет о безопасности, обычно наиболее предпочтительным методом является хранение токена в `httpOnly` cookie или передача его в заголовке `Authorization`.
  ]()

- [Из чего состоит `HTTP`-запрос?](https://youtu.be/w-vUj0gHGgg?t=483)
- [Какие методы может иметь `HTTP`-запрос?](https://youtu.be/G4iYlbilozM?t=419)
- [Что такое `HTTP` cookie? Для чего они используются?](https://youtu.be/G4iYlbilozM?t=488)
- [Разница между `HTTP` и `HTTPS`?](https://youtu.be/xZLxdts7ZW4?t=31)
- [Разница между `HTTP/1` и `HTTP/2`?](https://youtu.be/-mWa7erZu64?t=265)
- [Как работает мультиплексирование в `HTTP/2`?](https://youtu.be/-mWa7erZu64?t=378)
- [Что такое “трехстороннее рукопожатие” (Triple handshake)?](https://youtu.be/__neFkxAO9s?t=409)
- [Разница между `PUT`- и `POST`-запросами?](https://youtu.be/ngyOYuTrUk8?t=29)
- [Разница между протоколами `TCP` и `UDP`?](https://youtu.be/trriSYNrHw4?t=234)
- [Что такое `WebSocket`? В чем принцип его работы?](https://youtu.be/yvOXvZ8aEFo?t=237)
- [Разница между Long-Polling, Websockets и Server-Sent Events?](https://youtu.be/xZLxdts7ZW4?t=98)
- [Как работает `JSONP`?](https://youtu.be/trriSYNrHw4?t=178)
- [Что такое IndexedDB в браузере? Преимущества IndexedDB?](https://youtu.be/V-m0sQ-hW58?t=653)
- [Что такое Service Workers?](https://youtu.be/V-m0sQ-hW58?t=727)
- [Что такое Web Workers?](https://youtu.be/V-m0sQ-hW58?t=811)
- [Что такое Web Worklet?](https://youtu.be/__neFkxAO9s?t=521)
- [Что такое `SSL`/`TLS`? Зачем они используются в веб-разработке?](https://youtu.be/-mWa7erZu64?t=663)
- [Механизм устанавки сеанса между клиентом и сервером?](https://youtu.be/-mWa7erZu64?t=570)
- [Что Такое API?](https://youtu.be/ngyOYuTrUk8?t=98)
- [Что такое CDN?](https://youtu.be/ngyOYuTrUk8?t=152)
- [Что такое IP-адрес?](https://youtu.be/70VnuTXi4Wk?t=720)
- [Разница между host и domain?](https://youtu.be/70VnuTXi4Wk?t=779)
- [Разница между URI и URL?](https://youtu.be/70VnuTXi4Wk?t=844)
- [Почему очищать кэш важно? Как это можно сделать?](https://youtu.be/N1wPX5Z4HKE?t=30)
- [Разница между идентификацией, аутентификацией, авторизацией?](https://youtu.be/-mWa7erZu64?t=735)
- [Виды аутентификации?](https://youtu.be/-mWa7erZu64?t=770)
- [Что такое безопасные (Secure) и HttpOnly cookies?](https://youtu.be/ovV8GhIkzBE?t=158)
- [Что такое Content Security Policy (CSP)?](https://youtu.be/ovV8GhIkzBE?t=231)
- [Что такое CORS?](https://youtu.be/w-vUj0gHGgg?t=360)
- [Что такое межсайтовый скриптинг (XSS)?](https://youtu.be/ovV8GhIkzBE?t=292)
- [Методы повышения безопасности веб-приложений?](https://youtu.be/DZjIcc6KdjE?t=347)
- [Что такое OWASP Top 10?](https://youtu.be/DZjIcc6KdjE?t=419)
