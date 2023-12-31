# Проект №6 — Back-end тестирование №1.

Привет, участник Школы 21!🤗 В предыдущем блоке мы познакомились с ручным тестированием пользовательских интерфейсов, но этим, конечно же, ничего не ограничивается! Современные веб-приложения, как ты уже знаешь, постоянно взаимодействуют с серверами, которые тоже нужно уметь тестировать. В этом блоке ты познакомишься с API, сетевыми протоколами, HTTP-сообщениями, а также поработаешь со сваггером.

## Instructions

Напоминаем, что все отчёты по результатам выполнения заданий тебе нужно оформлять в файлах с расширением `.md`. Если они уже созданы, то пересоздавать или удалять их не нужно (просто отредактируй этот файл). Все созданные отчёты и файлы тебе нужно будет загрузить в папку `src/` в корне проекта (обязательно в ветку _develop_). 

## Contents 

1. [Chapter I](#chapter-i) \
    1.1. [Общая инструкция](#общая-инструкция) 
2. [Chapter II](#chapter-ii) \
    2.1. [Общее определение](#общее-определение) \
    2.2. [Что такое API и как он работает](#что-такое-api-и-как-он-работает) \
    2.3. [Способы работы API](#способы-работы-api) \
    2.4. [Сетевые протоколы](#сетевые-протоколы) \
    2.5. [Задание №1](#задание-1-http-сообщения) \
    2.6. [Основные методы запросов](#основные-методы-запросов) \
    2.7. [Задание №2](#задание-2-crud) \
    2.8. [Коды ответов](#коды-ответов) \
    2.9. [Задание №3](#задание-3-коды-ответов) 
3. [Chapter III](#chapter-iii) \
    3.1. [Тестирование API](#тестирование-api) \
    3.2. [Маршруты и эндпоинты](#маршруты-и-эндпоинты) \
    3.3. [Задание №4](#задание-4-эндпоинты) \
    3.4. [Swagger](#swagger) \
    3.5. [Задание №5](#задание-5-знакомство-с-функционалом-swagger) 

<h2 id="chapter-i">Chapter I</h2> 

<h3 id="общая-инструкция">Общая инструкция</h3>

Методология Школы 21 может быть не похожа на тот образовательный опыт, который случался с тобой ранее. Её отличает высокий уровень автономии: у тебя есть задача, ты должен её выполнить. По большей части тебе нужно будет самому добывать знания для её решения. Второй важный момент — это peer-to-peer обучение. В образовательном процессе нет менторов и экспертов, перед которыми ты защищаешь свой результат. Ты это делаешь перед такими же учащимися, как и ты сам. У них есть чек-лист, который поможет им качественно выполнить приёмку вашей работы.

Роль Школы 21 заключается в том, чтобы обеспечить через последовательность заданий и оптимальный уровень поддержки такую траекторию обучения, при которой ты не только освоишь hard skills, но и научишься самообучаться.

- Не доверяй слухам и предположениям о том, как должно быть оформлено ваше решение. Этот документ является единственным источником, к которому стоит обращаться по большинству вопросов;
- твоё решение будет оцениваться другими учащимися;
- подлежат оцениванию только те файлы, которые ты выложил в GIT (ветка develop, папка src);
- в твоей папке не должно быть лишних файлов — только те, что были указаны в задании;
- не забывай, что у вас есть доступ к интернету и поисковым системам;
- обсуждение заданий можно вести и в Rocket.Chat;
- будь внимателен к примерам, указанным в этом документе — они могут иметь важные детали, которые не были оговорены другим способом;
- и да пребудет с тобой Сила!

<h2 id="chapter-ii">Chapter II</h2>

<h3 id="общее-определение">Общее определение</h3>

В прошлом проекте мы упоминали, что клиент взаимодействует с сервером с помощью запросов. Но куда эти запросы отправляются и кем обрабатываются? Для этих задач и придумали **API**. 

**API (Application Programming Interface, программный интерфейс приложения)** — это механизмы, которые позволяют двум программным компонентам взаимодействовать друг с другом, используя набор определений и протоколов. Например, система ПО некоторого агентства содержит ежедневно обновляющиеся данные, тогда мобильное приложение этого агентства будет "общаться" с этой системой через API и показывать ежедневные обновления данных на телефоне.

<h3 id="что-такое-api-и-как-он-работает">Что такое API и как он работает</h3>

Акроним API дословно можно расшифровать как программный интерфейс приложения. В контексте API слово "приложение" относится к любому ПО с определённой функцией. Интерфейс можно рассматривать как сервисный контракт между двумя приложениями, который определяет, как они взаимодействуют друг с другом, используя запросы и ответы. А информацию о структуре этих запросов и ответов можно найти в документации API.

Архитектура API обычно объясняется с точки зрения клиента и сервера. Приложение, отправляющее запрос, называется **клиентом**, а приложение, отправляющее ответ, называется **сервером**. Таким образом, в примере выше база данных агентства — это сервер, а мобильное приложение — это клиент. 

<h3 id="способы-работы-api">Способы работы API</h3>

Существует четыре различных способа работы API в зависимости от того, когда и почему они были созданы.

#### **SOAP API**

**SOAP** — _Simple Object Access Protocol_, то есть простой протокол доступа к объектам. SOAP подразумевает использование _WSDL (Web Services Description Language)_ — язык описания веб-сервисов и доступа к ним, основанный на языке XML. То есть клиент и сервер обмениваются сообщениями посредством XML. Это менее гибкий API, который был популярен в прошлом.

#### **RPC API**

Такие API называются системой **удалённого вызова процедур**. Клиент выполняет функцию (или процедуру) на сервере, и сервер отправляет результат обратно клиенту.

#### **Websocket API**

**Websocket API** — это ещё одна современная разработка web API, которая использует объекты JSON для передачи данных. WebSocket API поддерживает двустороннюю связь между клиентскими приложениями и сервером. Сервер может отправлять сообщения обратного вызова подключённым клиентам, что делает его более эффективным, чем REST API.

#### **REST API**

На сегодняшний день это самые популярные и гибкие API-интерфейсы в Интернете. Клиент отправляет запросы на сервер в виде данных. Сервер использует этот клиентский ввод для запуска внутренних функций и возвращает выходные данные клиенту.

**REST (_Representational State Transfer_) API** — архитектурный стиль взаимодействия сайтов и веб-приложений с сервером. REST определяет набор функций, таких как GET, POST, DELETE и т. д., которые клиенты могут использовать для доступа к данным сервера. Клиенты и серверы обмениваются данными по протоколу HTTP.

Главная особенность REST API заключается в том, что такая передача выполняется без сохранения состояния. Это означает, что серверы не сохраняют клиентские данные между запросами. Важно отметить, что клиентские запросы к серверу в данном случае аналогичны URL-адресам, которые мы вводим в браузере для посещения веб-сайта, а ответ от сервера представляет собой простые данные без типичного графического отображения веб-страницы.

RESTful веб-сервисы, как правило, гораздо проще реализовать, чем, например, веб-сервисы на основе SOAP:

- REST обычно использует JSON, который легче анализировать и обрабатывать;
- В случае SOAP вам необходимо определить свой сервис с использованием WSDL;
- При обработке и анализе сообщений SOAP-XML возникают большие накладные расходы.

<h3 id="сетевые-протоколы">Сетевые протоколы</h3>

REST API, как было сказано выше, являются самыми популярными интерфейсами в Интернете. Они работают на базе протокола HTTP (HTTPS). Однако есть и другие сетевые протоколы.

**HTTP (HyperText Transfer Protocol)** — протокол для передачи информации (гипертекста), на базе которого функционируют все сегодняшние сайты. В его возможности входит процесс запрашивания необходимых данных у виртуально удаленной системы (файлы, веб-страницы и прочее).

**HTTPS (HyperText Transfer Protocol Secure)** — расширение протокола HTTP, поддерживающее шифрование данных, создавался с целью повышения безопасности.

**TCP (Transmission Control Protocol)** — один из основных протоколов передачи данных интернета, который является связующим звеном для установки качественного соединения между двумя устройствами, передачи данных и верификации их получения.

**IP (Internet Protocol)** — протокол, в функции которого входит корректность доставки сообщений по выбранному адресу. При этом информация делится на пакеты, которые могут поставляться по-разному.

**TCP/IP** — совокупность протоколов передачи информации. TCP/IP – это особое обозначение всей сети, которая функционирует на основе протоколов TCP, а также IP.

**UDP (User Datagram Protocol)** — протокол, управляющий передачей данных, но данные не проходят верификацию при получении. Этот протокол функционирует быстрее, чем протокол TCP.

**FTP (File Transfer Protocol)** — протокол передачи _файлов_ по сети. FTP-server в таком случае — это компьютер, предназначенный для хранения файлов.

**ICMP (Internet Control Message Protocol)** — протокол, который входит в стек протоколов TCP/IP. В основном ICMP используется для передачи сообщений об ошибках и других исключительных ситуациях.

**POP3, IMAP, SMTP** — это протоколы предназначенные для работы с почтой.

Из всех этих протоколов больше всего нас будут интересовать протоколы HTTP и HTTPS.

<h3 id="задание-1-http-сообщения">Задание №1. HTTP-сообщения</h3>

Пользуясь дополнительными источниками, попробуй найти информацию про HTTP-сообщения: что это такое, каких типов они бывают и какова их структура. Создай файл `exercise1.md`, запиши туда всю найденную информацию и озаглавь полученный текст как `## HTTP-сообщения`.

Также в этом файле опиши основные HTTP методы, при помощи которых создаются запросы к серверу (не меньше 7), указав, для чего используется каждый из них. Данный раздел текста озаглавь как `## HTTP методы`

<h3 id="задание-2-crud">Задание №2. CRUD</h3>

Создай файл `exercise2.md`, в который запиши определение акронима CRUD, а также что он означает в контексте REST API. 

<h3 id="коды-ответов">Коды ответов</h3>

Код ответа (статус-код) показывает, успешно ли был выполнен определённый HTTP запрос. Коды можно разделить на 5 классов:

- Информационные: 100 — 199
- Успешные: 200 — 299
- Перенаправления: 300 — 399
- Клиентские ошибки: 400 — 499
- Серверные ошибки: 500 — 599

<h3 id="задание-3-коды-ответов">Задание №3. Коды ответов</h3>

Перед выполнением этого задания познакомься с основными кодами ответов!

Представь, что ты тестируешь _GET-метод_, который нужен для запроса списка работников банка. В ходе тестирования ты можешь получить один из трёх вариантов ответа сервера:

1. Код ответа: `201`. Тело ответа:

```json
[
    {
        "name": "Малышева Екатерина Матвеевна",
        "birthday": "1995-06-01",
        "post": "Бухгалтер"
    },
    {
        "name": "Капустин Роман Артёмович",
        "birthday": "1991-01-18",
        "post": "Финансовый аналитик"
    },
    {
        "name": "Касьянов Ярослав Ярославович",
        "birthday": "1989-07-29",
        "post": "Кредитный эксперт"
    },
    {
        "name": "Белова Елизавета Руслановна",
        "birthday": "1997-04-13",
        "post": "Аудитор"
    },
    {
        "name": "Романов Константин Александрович",
        "birthday": "2001-12-14",
        "post": "Кассир"
    },
    ...
]
```

2. Код ответа: `400`. Тело ответа:

```json
{
  "message": "Неверные данные для авторизации."
}
```

3. Код ответа: `500`. Тело ответа:

```json
{
  "message": "Неверно составлен запрос."
}
```

Как ты думаешь, все ли ответы имеют верный статус-код? Если нет, то какой код должен быть в этих ответах? Запиши это в файл `exercise3.md` и озаглавь полученный раздел как `## Коды ответов`.

<h2 id="chapter-iii">Chapter III</h2>

<h3 id="тестирование-api">Тестирование API</h3>

**API Testing** — это тип тестирования программного обеспечения, во время проведения которого проверяются интерфейсы прикладного программирования (API). Целью API-тестирования является проверка функциональности, надёжности, производительности и безопасности интерфейсов программирования. В тестировании API вместо использования стандартных пользовательских входов (клавиатуры) и выходных данных используется программное обеспечение, предназначенное для отправки вызовов в API, получения выходных данных и записи ответа системы. Тесты API в отличие от GUI тестирования не концентрируются на внешнем виде приложения.

Пирамида тестов Майка Кона, которая представлена ниже, помещает тесты API на сервисный уровень (интеграционный). Это значит, что около 20% (или более) всех тестов должны быть сосредоточены на уровне API (точный процент зависит от наших потребностей).

![pyramid](misc/images/pyramid.png)

При наличии модульных тестов, покрывающих весь код, API тестирование позволяет проверить надёжность взаимодействия между клиентом и сервером.

<h3 id="маршруты-и-эндпоинты">Маршруты и эндпоинты</h3>

Когда мы говорим про API, часто можно встретить такие понятия как маршрут и эндпоинт. Рассмотрим их подробнее:

- **Маршрут (route)** — это "имя", которое отсылает работу API к определённым эндпоинтам. Можно сказать, что маршрут — это URL, к которому можно обратиться разными HTTP методами. Таким образом, маршрут может иметь несколько эндпоинтов.
- **Эндпоинт (endpoint)** — это само обращение к маршруту отдельным HTTP методом. Эндпоинты выполняют конкретную задачу, принимают параметры и возвращают данные клиенту.

<h3 id="задание-4-эндпоинты">Задание №4. Эндпоинты</h3>

А теперь представь, что тебе нужно придумать 4 эндпоинта для приложения, которое позволяет работать с рецептами новогодних блюд (просматривать, добавлять и прочее). Использовать нужно все методы CRUD. Какие это будут эндпоинты? Запиши их в файл `exercise4.md` (в нём уже есть несколько примеров 😉).

<h3 id="swagger">Swagger</h3>

Перед тестированием API нужно знать, какие методы реализованы на сервере, как и по какому URL'у к ним можно обратиться. Иными словами, нам нужна документация. **Swagger** — это набор инструментов, который позволяет автоматически описывать API на основе его кода или набора правил в формате JSON-файла.

**OpenAPI** — спецификация, по которой работает Swagger, но иногда название OpenAPI применяют при описании продукта.

**Swagger UI** — это инструмент, который визуализирует документацию, представляет её в более простом для понимания виде. Более того, она становится не просто визуальной, но и интерактивной, то есть с ней можно взаимодействовать - без написания кода, просто с помощью интерфейса.

<h3 id="задание-5-знакомство-с-функционалом-swagger">Задание №5. Знакомство с функционалом Swagger</h3>

Перейди в [Swagger тестового API](https://fakerestapi.azurewebsites.net/index.html). Это Fake REST API, который был разработан специально для ознакомления со Swagger UI. В файле `exercise5.md` опиши все возможные запросы (27 эндпоинтов). Каждое описание эндпоинта должно содержать:

1. HTTP-метод;
2. Полный URL запроса;
3. Заголовки запроса;
3. Тело запроса (при наличии);
4. Статус-код ответа;
5. Тело ответа (при наличии). Если тело большое, то только его часть;

Для GET-запроса с указанием `{id}` в запросе, а также для каждого PUT- или POST- запроса требуется описать два случая:
- успешный, когда сервер обрабатывает полученные данные _без ошибки_
- провальный, когда сервер обрабатывает полученные данные _с ошибками_ (к примеру, возращает 400 ошибку)

_P.S.: итого нужно описать 44 отправленных запроса_ 🤫.

<h3 id="double-check">Double-check</h3>

Перед загрузкой выполненного проекта в репозиторий перепроверь наличие всех необходимых файлов, которые требовалось создать во время его выполнения:

```
exercise1.md
exercise2.md
exercise3.md
exercise4.md
exercise5.md
```
💡 [Нажми здесь](https://forms.gle/37mimBmMrATvwHMb8) **чтобы отправить обратную связь по проекту**.
