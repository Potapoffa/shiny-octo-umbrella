# **Типы багов при тестировании программного обеспечения**
Существует множество различных типов дефектов программного обеспечения, и тестировщикам важно знать наиболее распространенные из них, чтобы они могли эффективно тестировать их.


Обычно мы можем видеть приоритет и серьезность классификаторов в большинстве инструментов отслеживания ошибок. Если мы настроим классификатор в соответствии с характером ошибки, а также приоритетом и серьезностью, это поможет легко управлять распределением обязанностей по исправлению ошибок соответствующим командам.


    1. Функциональные баги
Как следует из названия, функциональные баги — это те, которые вызывают сбои в работе программного обеспечения. Хорошим примером этого может служить кнопка, при нажатии на которую должно открываться новое окно, но вместо этого ничего не происходит.
Или же на странице не сохраняются внесенные данные.

Функциональные ошибки можно исправить, выполнив функциональное тестирование.
___
    2. Визуальные баги

Визуальные баги относятся к интерфейсу приложения.

Примеры:
- Кнопка "Сохранить" останется недоступной;
- Элемент управления сайтом наслаивается на нижестоящий элемент.
___
    3. Логические баги
Логические баги — это дефекты, из-за которых программа выдает неправильные результаты. Эти ошибки может быть трудно найти и исправить, потому что они часто не приводят к каким-либо видимым ошибкам. Логические ошибки могут возникать в любом типе программного обеспечения, но они особенно распространены в приложениях, требующих сложных вычислений или принятия решений.

Общие симптомы логических багов включают:

- Неверные результаты или выходные данные
- Неожиданное поведение
- Сбой или зависание программного обеспечения
___
    4. Дефекты юзабилити

Баги юзабилити — это дефекты, влияющие на работу пользователя с программным обеспечением и затрудняющие его использование. Дефект юзабилити — это дефект пользовательского опыта программного обеспечения, который затрудняет его использование. Ошибки юзабилити — это такие ошибки, как если веб-сайт сложен для доступа, или процесс регистрации сложен для прохождения.

___
    5. Дефекты производительности
Ошибки производительности — это дефекты, влияющие на производительность программного обеспечения. Это может включать в себя такие вещи, как скорость программного обеспечения, объем используемой памяти или количество потребляемых ресурсов. Ошибки уровня производительности сложно отследить и исправить, поскольку они могут быть вызваны рядом различных факторов.
___
    6. Дефекты безопасности
Ошибки безопасности — это тип дефекта программного обеспечения, который может иметь серьезные последствия, если его не устранить. Эти дефекты могут позволить злоумышленникам получить доступ к конфиденциальным данным или системам или даже позволить им получить контроль над уязвимым программным обеспечением. Таким образом, очень важно, чтобы ошибкам уровня безопасности уделялось первоочередное внимание и устранялись как можно скорее.

___
    7. Синтаксические ошибки
Синтаксические ошибки являются самым основным типом дефекта. Они возникают, когда код нарушает правила языка программирования. Например, использование неправильной пунктуации или забывание закрыть скобку может привести к синтаксической ошибке. Синтаксические ошибки обычно мешают запуску кода, поэтому их относительно легко обнаружить и исправить.
___
    8. Баги надежности
Баг надежностии - связан с неправильной работой программы при повторяемых условиях или высокой наргузке.

Примеры:
- в браузере открыто много вкладок, начинают долго загружаться, тормозить до тех пор, пока не закроют их или не перезапустят устройство;
- в момент игры на телефоне происходит прием телефонного звонка, при возврате в игру она сбивается.
___
    9. Баги нагрузки
Баг нагрузки - баг, в котором ПО должно выдерживать большую нагрузку на систему.

Примеры:
-  интернет-магазин должен выдержать большой наплыв посетителей
- все пользователи на сайте выбрали одну и ту же услугу.
___
    10.  Баги контента
Это баги в содержании, и связаны они с реальным содержанием веб-сайтов или приложений: текстом, этикетками, изображениями, видео, иконками, ссылками, данными и т.д.

Примеры:
- Отсутствующий текст, например, в пустой всплывающей подсказке 
- Неработающие ссылки или изображения (404s)
___
    11. Локализационные баги

Локализационный баг - баг, связанный с неверным отображением или переводом программы на другие языки.
    - выбрали язык "русский", все отображается на "английском";
    - выбрали страну Франция, отображается Россия.