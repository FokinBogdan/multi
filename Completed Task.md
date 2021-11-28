# IO-bound. Проверяем ссылки на страницах Википедии
## Синхронная проверка в 1 поток

Время работы: ![img.png](Image/img.png)
1151963 миллисекунды ≈ 19 минут 12 секунд.

Загрузка памяти: ![img_1.png](Image/img_1.png)

Загрузка процессора: ![img_2.png](Image/img_2.png)

## ThreadPoolExecutor

### max_workers = 5

Время работы: ![img_3.png](Image/img_3.png)
406331 миллисекунд ≈ 6 минут 46 секунд

Загрузка памяти: ![img_4.png](Image/img_4.png)

Загрузка процессора: ![img_5.png](Image/img_5.png)

Загрузка сети Internet: ![img_14.png](Image/img_14.png)

### max_workers = 10

Время работы: ![img_6.png](Image/img_6.png)
233960 миллисекунд ≈ 3 минуты 54 секунды

Загрузка памяти: ![img_7.png](Image/img_7.png)

Загрузка процессора: ![img_8.png](Image/img_8.png)

Загрузка сети Internet: ![img_13.png](Image/img_13.png)

### max_workers = 100

Время работы: ![img_9.png](Image/img_9.png)
179049 миллисекунд ≈ 2 минуты 59 секунд

Загрузка памяти: ![img_10.png](Image/img_10.png)

Загрузка процессора: ![img_11.png](Image/img_11.png)

Загрузка сети Internet: ![img_12.png](Image/img_12.png)

**Загрузка памяти не зависит от количества "воркеров".
При увеличении числа "воркеров": загрузка проццесора - увеличивается, загрузка сети Internet - увеличивается, время работы программы - уменьшается.
Используя ThreadPoolExecutor время работы уменьшается в несколько раз.**

# CPU-bound. Генерируем монетки
## Генерация монетки на 1 ядре

Время работы: ![](CPU-bound/Image CPU-bound/img.png)
155723 миллисекунды ≈ 2 минуты 36 секунд

Загрузка процессора: ![](CPU-bound/Image CPU-bound/img_1.png)

Загрузка памяти: ![img_2.png](CPU-bound/Image CPU-bound/img_2.png)

## ProcessPoolExecutor
### max_workers = 2

Время работы: ![img_3.png](CPU-bound/Image CPU-bound/img_3.png)
58010 миллисекунды ≈ 58 секунд

Загрузка процессора: ![img_4.png](CPU-bound/Image CPU-bound/img_4.png)

Загрузка памяти: ![img_5.png](CPU-bound/Image CPU-bound/img_5.png)

### max_workers = 4

Время работы: ![img_6.png](CPU-bound/Image CPU-bound/img_6.png)
126990 миллисекунды ≈ 2 минуты 7 секунд

Загрузка процессора: ![img_7.png](CPU-bound/Image CPU-bound/img_7.png)

Загрузка памяти: ![img_8.png](CPU-bound/Image CPU-bound/img_8.png)

### max_workers = 5

Время работы: ![img_9.png](CPU-bound/Image CPU-bound/img_9.png)
138878 миллисекунды ≈ 2 минуты 18 секунд

Загрузка процессора: ![img_10.png](CPU-bound/Image CPU-bound/img_10.png)

Загрузка памяти: ![img_11.png](CPU-bound/Image CPU-bound/img_11.png)

### max_workers = 10

Время работы: ![img_12.png](CPU-bound/Image CPU-bound/img_12.png)
122966 миллисекунды ≈ 2 минуты 3 секунды

Загрузка процессора: ![img_13.png](CPU-bound/Image CPU-bound/img_13.png)

Загрузка памяти: ![img_14.png](CPU-bound/Image CPU-bound/img_14.png)

### max_workers = 100

Ошибка: ![img_15.png](CPU-bound/Image CPU-bound/img_15.png)


**Загрузка памяти не зависит от количества "воркеров".
При увеличении числа "воркеров": загрузка проццесора - увеличивается, время работы программы - сначала уменьшается, но когда число "воркеров" достигает числа ядер процессора - не изменяется.**