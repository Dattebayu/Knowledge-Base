## Testing pyramid

`Пирамида тестирования` - специально разработанная структура, которая указывает на 
то как более эффективно использовать ресурсы и применять их. Заключается в том,
что у нас все тестирование разбивается на 3 части, в зависимости от их расположения
они выполняют в большем или меньшем количестве. Внизу пирамиды находятся юнит тесты
как самые дешевые, быстрые и эффективные, их больше всего так как они проверяют
непосредственно код по отдельности, на его работоспособность. Дальше идут тест
API, они являются более сложным, не такими быстрыми и требуют более высокой
квалификации, из-за этого их число должны быть меньше чем у юнит. И вверх пирамиды,
это ручное тестирование, так как они затрачивают меньше времени чем остальные 
и в большом количестве не нуждаются, так же они менее точные.

Применение данного метода обеспечит:
- увеличение скорости выполнения тестов
- экономия времени и ресурсов
- группировка тестирование по типам
- снижение рисков возникновения

