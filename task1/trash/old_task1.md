# Задание 1. Формализация ПДД

## Требования
Необходимо формализовать модель правил дорожного движения для их последующего использования.
То есть должен быть набор правил, с помощью которых можно будет двигаться по ДОПам на автомобиле.

## Реализация
Если нет препятствий, то продолжаем движение с мин(разрешенная скорость; скорость, на которой гарантируется сохранение свойств управляемости транспорта).

Препятствиями могут являться: другие ТС, пешеходы, прочие объекты, если они мешают движению ТС.

### Термины (объекты, взаимодействующие друг с другом)

На дорогах могут присутствовать только субъекты (С) и объекты (О).
Субъектами являются: водители ТС (В) и пешеходы (П).
Объектами являются: дорожные знаки, вертикальная и горизонтальная разметка, проезжая часть, светофор...
Дорожные знаки могут быть: запрещающие, предписывающие, сервиса, предупреждающие...
Дорожная разметка может быть: сплошная, штриховая.
Перекресток может быть: регулируемый, нерегулируемый.
Регулировщиком может быть: сотрудник полиции или светофор.
Зона может быть: проезжей частью, прилежащей...
Движение может быть: разрешено, запрещено.
Препятствиями могут являться: ТС, пешеходы...
Скорость движения может быть: 0..139.
Тип движения: вперед, назад, маневр.
Маневр: поворот налево, направо, разворот, обгон, перестроение.
Светофор может быть с отдельной секцией для направления движения или без дополнительной секции.

### Правила взаимодействия

#### Общие правила движения

1. Если зона является проезжей частью, то движение по ней разрешено.
2. Если зона является прилежащей частью, то движение по ней разрешено.
3. Если зона не является проезжей или прилежащей, то движение по ней запрещено.
4. Если на пути следования нет препятствий, то движение разрешено.
5. Если на пути следования есть препятствия, то движение запрещено.
6. Скорость движения выбирается как min(максимальная разрешенная скорость на участке; максимальная скорость, при которой сохраняется управляемость).
7. 

#### Правила проезда перекрестков

1. Если перекресток регулируется светофором, и он светит зеленым, то можно продолжать движение.
2. Если перекресток регулируется светофором, и он светит желтым, то необходимо прекратить движение.
3. Если перекресток регулируется светофором, и он светит красным, то необходимо прекратить движение.
4. Если перекресток нерегулируемый, 

#### Правила обгона

Обгон разрешён,
если:
    1) отсутствует знак "обгон запрещен";
    2) ваш ТС =не обгоняет другой ТС;
    3) разметка на проезжей части не является сплошной;
    4) до пешеходного перехода ещё n метров;
    5) до ЖД переезда ещё k метров;
    6) ТС не двигается по ... (нерегулируемый перекресток, второстепенная...)

#### Правила стоянки
ТС может быть поставлен на стоянку в данном месте,
если:
    1) отсутствует запрещающий знак;
    2) до ближайшего пешеходного перехода 5 метров;
    3) до ЖД переезда {} метров;

#### Правила парковки
ТС может быть припаркован,
если:
    1) отсутствует запрещающий знак;
    2) до пешеходного перехода 5 метров;
    3) до ...

#### Правила перехода пешеходного перехода

1. Если переход регулируется светофором, то пешеход ждёт зеленого сигнала, а затем переходит.
2. Если переход не регулируется светофором, то пешеход переходит сразу, как только будет возможность.

#### Правила проезда ЖД переездов

