# Мобильные приложения (mobile apps) – это программы, которые предназначены для той или иной платформы (Android, iOS, Windows 10 Mobile, BlackBerry и многие другие), написаны на языке высокого уровня и позволяют выполнять различные действия в зависимости от своего функционала.
Неотъемлемой частью разработки  приложений является их тестирование. Мобильное тестирование – сложный процесс: десятки различных разрешений экрана, аппаратные отличия, несколько версий операционных систем, разные типы подключения к Интернету, внезапные обрывы связи.
Основные моменты и особенности тестирования мобильных приложений, на которые стоит обратить внимание при функциональном и GUI тестировании мобильных приложений.
## Особенности тестирования мобильных приложений

*Нужно учесть все модели гаджетов*
Необходимо помнить про существование различных версий операционных систем гаджетов, технических характеристик девайсов. Поэтому следует еще на старте собрать статистические данные, чтобы понять, какой модельный ряд смартфонов, планшетов пользуется популярностью у целевой аудитории, и выполнять проверку на таких гаджетах.

*Проводить тестирование браузеров, старой и новой версии ОС*
Если утилита не поддерживает операционную систему, установленную на устройстве пользователя, он не получит возможность ее загрузить на смартфон или планшет. Разработчики ПО, зная такую особенность, способны поставить специальную заглушку с уведомлением о том, что браузер или операционную систему необходимо обновить до определенной версии.

*Осуществить тест-кейсы*
Специалист обязательно должен учесть абсолютно все способы контакта целевой аудитории с мобильным программным обеспечением. Поэтому создаются тест-кейсы с четким описанием каждого действия, необходимого для проверки определенной опции. Они базируются исключительно на пользовательских сценариях – подробных схемах, которые предоставляют информацию о том, как представители целевой аудитории решают возникающие задачи при помощи программ, и аспектах, им мешающих в этом.

*Удостовериться в удобстве новой версии*
Обновление программного обеспечения не должно сопровождаться проблемами, ошибками. Поэтому при тестировании мобильных приложений чек-лист обязательно должен содержать пункт, посвященный выяснению того, как будет вести утилита себя, если пользователи не выполнили обновление версии самостоятельно.

*Функционирование при плохом сигнале сети*
Специалисту обязательно нужно проанализировать и проверить все ситуации использования ПО, в том числе с проблемами с интернет-соединением. Важно добиться, чтобы у мобильной утилиты была аналогичная ответная реакция на все ситуации с плохим сигналом Wi-Fi.

*Протестировать коммуникацию пользователя с интерфейсом*
Начинающие тестировщики практически всегда стараются найти в тестировании мобильного приложения пример и отталкиваться от него в своей будущей работе. В обязательном порядке специалист должен проверять программу на:

- функциональность;
- безопасность;
- уровень производительности;
- комфорт, удобство пользования.
При этом необходимо учесть абсолютно каждую деталь: от параллельного использования с иным ПО до корректировки шрифта, размера. Приведем пример – нативные программы могут использовать встроенные опции гаджета. Например, микрофон и на устройствах с ОС iOS они должны запросить разрешение на его задействование.

## Инструментарий
Важно правильно подобрать на тестирование мобильных приложений инструменты.  **Эмулятор (emulator)** – программа, полностью или частичнокопирующая функции и поведение устройства или другой программы.

Некоторые из *преимуществ* использования эмулятора:

- оперативное тестирование приложения, когда целевой мобильный телефон недоступен (или оказывается в дефиците);

- тестирование сложных или опасных сценариев, которые невозможно или не рекомендуется проверять на реальных мобильных телефонах (например, тесты, которые каким-либо образом могут вывести телефон из строя или нарушить условия соглашения с оператором сотовой связи).

*Минусы*:

- зачастую эмуляторы очень требовательны к ресурсам, так как наиболее качественные из них эмулируют работу приложения с самых нижних уровней;

- то, что приложение работает на эмуляторе, не значит практически ничего, ведь пользователи будут запускать приложения на реальных мобильных телефонах, которые всегда отличаются даже от самых лучших эмуляторов.

Эмуляторы незаменимы при тестировании верстки и геолокации. При этом нужно понимать, что эмулятор никогда не заменит реальное устройство.

**DevTools**. Идеальный вариант для тестирования ПО в веб-браузере. С помощью такого инструмента можно проверить скорость соединения с сетью, адаптивность верстки и корректность смены ориентации экрана.Тестировать мобильное веб-приложение можно в обычном браузере на компьютере с помощью инструмента DevTools. Он помогает проверить адаптивность вёрстки, смену ориентации экрана, разные скорости интернет-соединения
**Сервисы Beta, TestFlight**. Это программное обеспечение идеально подходит для выполнения бета-тестирования.Активная работа по выявлению ошибок, влияющих на корректную работу приложения, производится на этапе бета-тестирования — использования практически готовой версии перед окончательным запуском. Для бета-тестирования мобильных приложений используют сервисы TestFlight для iOS и Beta для Android.
**Снифферы**. Такой инструмент используется для проверки корректности взаимодействия с бэкэндом. При помощи снифферов можно анализировать https-запросы, разные коды ответных действий и реакцию программного обеспечения.Для тестирования взаимодействия с бэкендом — частью приложения, работающей на сервере, — применяют снифферы. Сниффер — это анализатор трафика, то есть всей информации, которая проходит через компьютерные сети. С его помощью можно проверять http-запросы, различные коды ответов и реакцию приложения на них. Самые популярные снифферы — Fiddler и Charles.
## Все мобильные приложения можно разделить на несколько категорий:

**Веб-приложения** – кросс-платформенные приложения позволяют отображать сайты на различных устройствах.
Веб-приложения отличаются кросс-платформенностью, простотой в разработке и невысокой производительностью: загрузка файлов и обработка действий пользователя занимают больше времени, чем в нативном приложении.Работают через веб-браузер на устройстве пользователя. По сути, это кастомизированные веб-сайты, которые выглядят как настоящие приложения, но размещаются не на устройстве пользователя. Вы открываете с телефона, планшета, ноутбука или стационарного устройства ПК (веб-приложение работает не только на мобильных девайсах) страничку в Интернете, которая “косит” под приложение. Это похоже на хранение данных в облаке или на жестком диске компьютера. Часто веб-приложение дополняет мобильное нативное приложение и наоборот. При качественной разработке веб-приложения работают почти как нативные. Разберемся в этом “почти”, в чем же разница?

Преимущества:

- веб-приложения могут функционировать на платформе с любой ОС;
- разработчикам не нужно утверждать приложение с магазинами;
- цикл разработки CSS, HTML и JavaScript идет в разы быстрее.

Недостатки:

- нет доступа к аппаратной части устройств пользователей, что значительно урезает функционал веб-приложений (например, невозможно сделать веб-приложение, которое задействует акселерометр на устройстве или включит камеру);
- использование возможно только через Интернет и зависит от его наличия, скорости и стабильной работы;
- приложения не каталогизированы в одном месте и их сложнее искать.

пример- Телеграм, Skype

**Нативные приложения** разработаны только под определенную платформу и по максимуму используют возможность той или иной операционной системы.
Нативные приложения сложные и дорогие в разработке, но у них высокая скорость работы,  и они позволяют задействовать разные функции телефона — например, камеру.
"Native" с английского — «родной». Нативное мобильное приложение — это приложение, которое создается под конкретную платформу. Нативное мобильное приложение написано на «родном» для платформы языке программирования: для Android — Kotlin и Java, для Apple iOS — Objective-C и Swift.

Нативное мобильное приложение имеет доступ ко всем нативным технологиям и аппаратным возможностям конкретной платформы. Нативные мобильные приложения необходимо загружать и устанавливать на устройство, например, через официальные магазины Google Play Market и App Store.

Преимущества:

- доступ к аппаратной части устройства (геолокации, камере, микрофону, акселерометру, датчикам освещенности, календарю, push-уведомлениям) и широкий функционал за счет этого;
- могут закрыть больше различных запросов заказчиков и пользователей;
- данные пользователя можно легко собирать и анализировать;
- обычно, работают более стабильно и эффективно с любыми применяемыми девайсами на своей ОС;
- нет ограничения функционала скоростью и качеством Интернет-соединения, приложение может работать без выхода в сеть;
- лучше подходят для проектов с кастомизированными интерфейсами и сложной бизнес-логикой.

Недостатки:

- дорогие в разработке;
- для разработки нужно больше времени;
- проходят верификацию каждым магазином приложений;
- охватывают мало платформ и несовместимы с другими операционными системами;
- даже легкие изменения требуют регулярных обновлений.
 В зависимости от предназначения нативного приложения, оно может всецело или частично обходиться без наличия интернет-соединения
 
пример-Instagram

**Гибридные приложения** 
Гибридные приложение — компромисс между нативными и веб-приложениями. Они размещаются в рамках нативного приложения и работают через WebView. У них есть доступ к информации на устройстве пользователя.

Выглядят и используются как нативные приложения: их можно скачать из магазина и установить на устройство. Установка может оказаться номинальной, так как такие приложения имеют доступ к данным пользователя, но часто сами не хранят свои данные непосредственно на устройстве пользователя.

WebView — это системный компонент, который открывает веб-страницы в рамках других приложений. Когда вы открывали ту или иную ссылку в социальной сети или клиенте электронной почты, то она открывалась в интерфейсе самой социальной сети или клиенте электронной почты, вместо перехода в браузер. Это работа WebView.

Преимущества:

- широкий функционал и высокая степень кастомизации;
- можно создать приложение, которое будет работать с несколькими платформами;
- удешевляют и ускоряют разработку MVP или несложного готового продукта для заказчиков;
- являются серединным решением между функционалом и производительностью нативного приложения и дешевизной веб-приложения.

Недостатки:

- слишком сложные приложения лучше делать нативными, как и приложения с громоздкими визуальными решениями вроде игр;
- разработка потребует больше времени и усилий, чтобы гибридное приложение выглядело и ощущалось как нативное;
- магазины приложений отклоняют недостаточно хорошо работающие гибридные приложения и важно соблюдать стандарты качества.

пример- Uber

## Различие в тестировании нативных, гибритных и веб-приложений . 
Приложения, основанные на трех разных подходах (native, web и гибридный) имеют различные сценарии. Они значительно различаются по показателям производительности и совместимости. Родные и гибридные приложения должны быть протестированы для успешного выполнения, загрузки, взаимодействия с платформой и поведения при обновлении. Приложения, ориентированные только на веб-сайты, в большей степени зависят от выбора браузера и его версий, в которых должны проверяться все экземпляры.

**Веб-приложения**
Тестирование веб-приложений включает в себя тестирование пользовательского интерфейса, проверку использования батареи, выявление проблем с подключением и отслеживание узких мест, вызванных рекламой.

Задачи тестирования WEB-приложений:

- Нахождение ошибок в работе программы и эффективное их устранение;
- Проверка приложения на соответствие конкретным требованиям;
- Проверка качества работы создателей приложения;
- Обработка информации, которая станет основой для принятия последующих действий.

**Нативные приложения**
Тестирование нативных приложений включает в себя проверку работоспособности приложения на различных устройствах и операционных системах, а также проверку совместимости с различными версиями операционной системы и различными разрешениями экрана.
**Гибридные приложения**
Тестирование гибридных приложений включает в себя проверку совместимости приложения с различными операционными системами и различными разрешениями экрана.

Нативные и гибридные приложения проходят тестирование экрана, сети, совместимости и жестов, а также другие испытания.


Нативные и гибридные приложения используют разные базовые технологии, но они схожи с точки зрения предоставляемой функциональности - следовательно, подход к тестированию будет одинаковым для обоих типов приложений.
Для функционального тестирования  необходимо убедиться, что все функции приложения работают должным образом.