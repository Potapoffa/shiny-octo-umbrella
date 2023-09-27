# ID 1. Failed to load resource: the server responded with a status of 404 () datago

Предшествующие условия:

1. Открыта страница сайта https://sbermegamarket.ru/

**Серьезность:**
Trivial

**Приоритет:**
Normal

Шаги:

1. Открыть панель разработчика DevTools (Ctrl+Shift+J или F12)
2. В DevTools открыть консоль
3. Установить фильтр "Ошибки"

Ожидаемый результат

1. Запрос выполнен, загружен элемент https://stream.datago.ru/mp/collect?tid=UA-89387429-1
2. Результат 200 OK

Фактический результат:

1. Ошибка 404

Окружение
Mozilla Firefox.Версия 114.0.2 (64-разрядный)
Windows 11 Домашняя. Версия 10.0.22621 Сборка 22621

# ID 2. Не удалось выполнить запрос CORS

Предшествующие условия:

1. Открыта страница сайта https://sbermegamarket.ru/
2. Нажать иконку "Войти"

**Серьезность:**
Trivial

**Приоритет:**
Normal

Шаги:

1. Открыть панель разработчика DevTools (Ctrl+Shift+J или F12)
2. В DevTools открыть консоль
3. Установить фильтр "Ошибки"

Ожидаемый результат

1. Запрос выполнен, загружен элемент https://wcm.weborama-tech.ru/fcgi-bin/dispatch.fcgi?a.A=im&a.si=9312&a.te=2&a.he=1&a.wi=1&a.hr=p&a.ycp=1614819040.1687725787

2. Результат 200 OK

Фактический результат:

1. Запрос из постороннего источника заблокирован: Политика одного источника запрещает чтение удаленного ресурса на https://cms-res.online.sberbank.ru/sberid/BlackList/Button/No_Button.json. (Причина: не удалось выполнить запрос CORS). Код состояния: (null).

Окружение
Mozilla Firefox.Версия 114.0.2 (64-разрядный)
Windows 11 Домашняя. Версия 10.0.22621 Сборка 22621

# ID 3. Ошибка загрузки https://id.sber.ru/CSAFront/api/userdata?client_id=52cd75e2-76e1-43ba-ade6-938b2c7d4e7a

Предшествующие условия:

1. Открыта страница сайта https://sbermegamarket.ru/
2. Нажать иконку "Войти"


**Серьезность:**
Trivial

**Приоритет:**
Normal

Шаги:

1. Открыть панель разработчика DevTools (Ctrl+Shift+J или F12)
2. В DevTools открыть консоль
3. Установить фильтр "Ошибки"

Ожидаемый результат

1. Запрос выполнен, загружен элемент https://id.sber.ru/CSAFront/api/userdata?client_id=52cd75e2-76e1-43ba-ade6-938b2c7d4e7a

2. Результат 200 OK

Фактический результат:

1. Ошибка 400 Bad Request

Окружение
Mozilla Firefox.Версия 114.0.2 (64-разрядный)
Windows 11 Домашняя. Версия 10.0.22621 Сборка 22621

# ID 4. Failed to load resource: the server responded with a status of 502 (Bad Gateway)

Предшествующие условия:

1. Открыта страница сайта https://sbermegamarket.ru/
2. Нажать "Стать продавцом" в хэдере.

**Серьезность:**
Trivial

**Приоритет:**
Normal

Шаги:

1. Открыть панель разработчика DevTools (Ctrl+Shift+J или F12)
2. В DevTools открыть консоль
3. Установить фильтр "Ошибки"

Ожидаемый результат

1. GET запрос выполнен, загружен элемент https://sbermegamarketru.webim.ru/button.php
2. Результат 200 OK

Фактический результат:

1. GET запрос не выполнен
2. Получен статус-код 502 (Bad Gateway)

Окружение
Mozilla Firefox.Версия 114.0.2 (64-разрядный)
Windows 11 Домашняя. Версия 10.0.22621 Сборка 22621


# ID 5. Запрос из постороннего источника заблокирован (vk)

Предшествующие условия:

1. Открыта страница сайта https://sbermegamarket.ru/
2. Нажать "Стать продавцом" в хэдере.

**Серьезность:**
Trivial

**Приоритет:**
Normal

Шаги:

1. Открыть панель разработчика DevTools (Ctrl+Shift+J или F12)
2. В DevTools открыть консоль
3. Установить фильтр "Ошибки"

Ожидаемый результат

1. Отсутствие ошибок

Фактический результат:

1. В консоли отражается несколько ошибок "Запрос из постороннего источника заблокирован: Политика одного источника запрещает чтение удаленного ресурса на...":
    - https://vk.com/rtrg?p=VK-RTRG-1522272-gSw6t&products_event=view_other&price_list_id=1&e=1&i=0&metatag_url=%2F%2Fsbermegamarket.ru%2Finfo%2Fpartners%2F&metatag_title=%D0%A1%D0%B1%D0%B5%D1%80%D0%9C%D0%B5%D0%B3%D0%B0%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%20-%20%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0%D0%BC%20-%20%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%BF%D0%BB%D0%B5%D0%B9%D1%81%20SberMegaMarket.ru
    - https://vk.com/rtrg?p=VK-RTRG-740345-e0KWW&products_event=view_other&price_list_id=1&e=1&i=0&metatag_url=%2F%2Fsbermegamarket.ru%2Finfo%2Fpartners%2F&metatag_title=%D0%A1%D0%B1%D0%B5%D1%80%D0%9C%D0%B5%D0%B3%D0%B0%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%20-%20%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0%D0%BC%20-%20%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%BF%D0%BB%D0%B5%D0%B9%D1%81%20SberMegaMarket.ru
    - https://vk.com/rtrg?p=VK-RTRG-1042270-gnJEy&products_event=view_other&price_list_id=140664&e=1&i=0&metatag_url=%2F%2Fsbermegamarket.ru%2Finfo%2Fpartners%2F&metatag_title=%D0%A1%D0%B1%D0%B5%D1%80%D0%9C%D0%B5%D0%B3%D0%B0%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%20-%20%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0%D0%BC%20-%20%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%BF%D0%BB%D0%B5%D0%B9%D1%81%20SberMegaMarket.ru
    - https://vk.com/rtrg?p=VK-RTRG-1392950-ns48&products_event=view_other&price_list_id=1&e=1&i=0&metatag_url=%2F%2Fsbermegamarket.ru%2Finfo%2Fpartners%2F&metatag_title=%D0%A1%D0%B1%D0%B5%D1%80%D0%9C%D0%B5%D0%B3%D0%B0%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%20-%20%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0%D0%BC%20-%20%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%BF%D0%BB%D0%B5%D0%B9%D1%81%20SberMegaMarket.ru
    - https://vk.com/rtrg?p=VK-RTRG-934121-8M7uZ&products_event=view_other&price_list_id=1&e=1&i=0&metatag_url=%2F%2Fsbermegamarket.ru%2Finfo%2Fpartners%2F&metatag_title=%D0%A1%D0%B1%D0%B5%D1%80%D0%9C%D0%B5%D0%B3%D0%B0%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%20-%20%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0%D0%BC%20-%20%D0%9C%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%BF%D0%BB%D0%B5%D0%B9%D1%81%20SberMegaMarket.ru

Окружение
Mozilla Firefox.Версия 114.0.2 (64-разрядный)
Windows 11 Домашняя. Версия 10.0.22621 Сборка 22621


# ID 5. Open api access error (vk)

Предшествующие условия:

1. Открыта страница сайта https://sbermegamarket.ru/
2. Нажать "Стать продавцом" в хэдере.

**Серьезность:**
Trivial

**Приоритет:**
Normal

Шаги:

1. Открыть панель разработчика DevTools (Ctrl+Shift+J или F12)
2. В DevTools открыть консоль
3. Установить фильтр "Ошибки"

Ожидаемый результат

1. Отсутствие ошибок

Фактический результат:

1. В консоли отражается несколько ошибок "Open api access error"


Окружение
Mozilla Firefox.Версия 114.0.2 (64-разрядный)
Windows 11 Домашняя. Версия 10.0.22621 Сборка 22621

# ID 6. DDManager Custom Event "Clicked ToCart Button (Desktop + Mobile Main Icon)" 

Предшествующие условия:

1. Открыта страница сайта https://sbermegamarket.ru/
2. Нажать "Корзина" в хэдере.

**Серьезность:**
Trivial

**Приоритет:**
Normal

Шаги:

1. Открыть панель разработчика DevTools (Ctrl+Shift+J или F12)
2. В DevTools открыть консоль
3. Установить фильтр "Ошибки"

Ожидаемый результат

1. Отсутствие ошибок

Фактический результат:

1. В консоли отражается ошибка "TypeError: DDManager Custom Event "Clicked ToCart Button (Desktop + Mobile Main Icon)" Error"


Окружение
Mozilla Firefox.Версия 114.0.2 (64-разрядный)
Windows 11 Домашняя. Версия 10.0.22621 Сборка 22621