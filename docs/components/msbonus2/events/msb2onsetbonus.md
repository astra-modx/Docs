# msb2OnSetBonus

Срабатывает после применения бонусов к корзине или заказу.

## Параметры

- `numeric $points` — общее кол-во бонусов у юзера
- `numeric $amount` — кол-во бонусов введённых юзером для списания
- `null|msOrder $order` — объект заказа `msOrder` или `null`, если бонусы применяются к корзине
- `numeric $writeoff` - кол-во списанных бонусов