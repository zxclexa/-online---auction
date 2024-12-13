## Описание

Проект состоит из двух классов:

- **Lot**: Описание отдельного лота, включая название, описание, начальную ставку, текущую ставку и время завершения аукциона.
- **Auction**: Управляет коллекцией лотов и позволяет пользователям делать ставки на них.

## Структура 

### Класс `Lot`

- `title`: Название лота.
- `description`: Описание лота.
- `starting_bid`: Начальная ставка.
- `end_time`: Время окончания торгов для лота.
- `current_bid`: Текущая ставка на лот.
- `highest_bidder`: Имя пользователя, который сделал наибольшую ставку.

Методы:

- `__init__(self, title, description, starting_bid, end_time)`: Инициализация лота.
- `place_bid(self, bid_amount, bidder_name)`: Размещение ставки на лот.
- `__str__(self)`: Строковое представление лота.

### Класс `Auction`

- `add_lot(self, lot)`: Добавление лота в аукцион.
- `show_lots(self)`: Отображение всех лотов.
- `place_bid(self, lot_index, bid_amount, bidder_name)`: Размещение ставки на конкретный лот по индексу.

## Пример использования

```python
import datetime

# Создание лотов
lot1 = Lot("Картина маслом", "Красивый пейзаж", 100, datetime.datetime(2024, 3, 15, 20, 0, 0))
lot2 = Lot("Старинная книга", "Редкое издание", 50, datetime.datetime(2024, 3, 10, 12, 0, 0))
lot3 = Lot("Кофеварка", "Новая, в упаковке", 20, datetime.datetime(2024, 3, 12, 18, 0, 0))
lot4 = Lot("Набор инструментов", "Профессиональный", 150, datetime.datetime(2024, 3, 14, 10, 0, 0))
lot5 = Lot("Антикварная ваза", "Китайская фарфоровая ваза", 300, datetime.datetime(2024, 3, 16, 15, 0, 0))

# Создание аукциона и добавление лотов
auction = Auction()
auction.add_lot(lot1)
auction.add_lot(lot2)
auction.add_lot(lot3)
auction.add_lot(lot4)
auction.add_lot(lot5)

# Показ всех лотов
auction.show_lots()

# Размещение ставок
auction.place_bid(0, 150, "Иван")
auction.place_bid(0, 120, "Петр")
auction.place_bid(1, 75, "Мария")

# Показ лотов после ставок
auction.show_lots()
