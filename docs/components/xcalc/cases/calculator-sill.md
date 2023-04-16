# Калькулятор подоконников

Давайте попробуем воспроизвести [пример калькулятора с демо-сайта][1].
Заходим на страницу компонента в бек-энде.

## Шаг 1

Первым делом создадим поля для нашего калькулятора. Для этого переходим во вкладку "Поля" и по-очереди создаём необходимые нам.
**Обратите внимание**, что значения для поля можно задать только после его добавления. По сути, оно должно быть в базе, чтобы привязать к нему значения.
**Также**, если вы добавляете поле `msProducts`, то нужно понимать, что вместо значений для него забиваются параметры сниппета `msProducts` в формате JSON.

### Ширина (мм)

- Тип: `Число`
- Ключ: `width`
- По-умолчанию: `1900`
- Обязательно: `Да`

### Длина (мм)

- Тип: `Число`
- Ключ: `length`
- По-умолчанию: `500`
- Обязательно: `Да`

### Материал

- Тип: `msProducts`
- Ключ: `material`
- Обязательно: `Да`
- Значения:
  - Параметры (JSON):

```json
{
  "parents": 5,
  "where": {},
  "sortby": {"parent":"ASC", "menuindex":"ASC"},
  "limit": 0
}
```

### Профиль

- Тип: `Radiobox`
- Ключ: `chamfer`
- По-умолчанию: `1500`
- Обязательно: `Да`
- Значения:
  - Профиль Zx: `1500`
  - Профиль V: `2200`
  - Профиль H: `2500`
  - Профиль F '3: `3000`
  - Профиль E: `1800`
  - Профиль B: `1950`
  - Профиль A: `180`
  - Профиль F: `3500`

### Монтаж подоконника

- Тип: `Checkbox`
- Ключ: `mounting`
- Значения:
  - Монтаж подоконника 200 мм: `1800`
  - Монтаж подоконника 300 мм: `2000`
  - Монтаж подоконника 400 мм: `2200`
  - Монтаж подоконника 500 мм: `2300`
  - Монтаж подоконника 600 мм: `2500`

#### Ухо подоконника

- Тип: `Checkbox`
- Ключ: `ear`
- Значения:
  - Подрезка уха подоконника: `300`

## Шаг 2

Теперь нам нужно создать объект калькулятора, в котором мы соберём все необходимые поля. На вкладке "Калькуляторы" создаём:

- Заголовок: `Калькулятор подоконников`
- Сниппет: `xcc.results`

Сниппет - это наш обработчик результатов расчёта.
В комплекте с компонентом, в качестве примера поставляется сниппет `xcc.results`, рассчитанный как раз на данный калькулятор. Поэтому править нам его не нужно. Однако, если вам что-то надо добавить, то сниппет хорошо задокументирован.

Сохраняем.

## Шаг 3

Сейчас нам надо привязать к калькулятору недавно созданные поля.
На только что созданном калькуляторе жмём "Редактировать", откроется окошко, в нём переходим во вкладку "Поля".
Жмём кнопку "Добавить" и по-очереди добавляем в калькулятор нужные поля. При желании можно перетащить поля вверх или вниз, таким образом сортируя вывод полей в форме на фронт-энде.

## Шаг 4

Вывести калькулятор на фронте достаточно просто:

```fenom
{'!xCalc' | snippet : [
  'id' => 1,
  'tplOuter' => 'tpl.xCalc.outer',
  'tplResults' => 'tpl.xCalc.results',
]}
```

В параметр `id` указываем ID нового калькулятора.
В параметр `tplResults` указываем чанк вывода результатов расчёта. В комплекте с компонентом в чанке `tpl.xCalc.results` настроен вывод, рассчитанный на данный калькулятор.

[1]: http://xcc.h1.gvozdb.ru/index.php?id=18