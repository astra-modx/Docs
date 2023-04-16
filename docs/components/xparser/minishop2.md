# Работа с miniShop2 товарами

С версии 1.5.0 в компонент добавлена поддержка свойств/опций miniShop2 товаров.
Начиная с этой версии появилась возможность парсить товары магазина.

## Особенности

Есть ряд особенностей, которые следует соблюдать, при создании miniShop2 товаров при помощи xParser.

1. В конфигурации задания нужно выбрать раздел с типом «Категория товаров».
2. В полях задания нужно создать поле **resource | class_key**, со значением по-умолчанию: `msProduct`
3. Для корректной выгрузки таких полей, как `tags`, `color`, `size` и т.п. при создании полей задания была добавлена настройка **Раскодировать JSON строку в массив**. Дело в том, что при создании товаров через процессор, miniShop2 ждет от нас PHP массив для этих полей, поэтому для корректной выгрузки полей такого типа, нужно раскодировать JSON в PHP. К примеру, вот:

![Особенности](https://file.modx.pro/files/4/0/f/40ffc7e65359342dd91976e475c6bd38.png)

Все остальные действия типовые. Почитать подробнее можно в разделах:

- [Парсер RSS лент][1]
- [Парсер HTML контента + Совмещенные задания][2]

[1]: /components/xparser/parser-rss
[2]: /components/xparser/parser-html