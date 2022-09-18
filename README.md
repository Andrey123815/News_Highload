# News_HighLoad
Технопарк Mail.ru 3 семестр. Домашнее задание №1 по курсу "HighLoad".

## Содержание
1. [Тема и целевая аудитория](#1)
2. [Расчет нагрузки](#2)
3. [Логическая схема](#3)
4. [Физическая схема](#4)
5. [Технологии](#5)
6. [Схема проекта](#6)
7. [Список серверов](#7)
8. [Список использованных источников](#8)


## 1. Тема и целевая аудитория <a name="1"></a>

**Яндекс Дзен** - сервис индивидуальных рекомендаций Яндекса, который за время подгрузки браузерной страницы с поиском автоматически подготавливает ленту релевантных интересам пользователя статей.

### MVP
- авторизация
- просмотр новостных статей (текст, изображения, видео)
- просмотр и оценивание постов (1,5 тысячи знаков с картинками не больше 10 штук)
- оставление комментариев к постам ()
- просмотр и оценивание роликов (видео продолжительностью до 1 минуты)
- просмотр и оценивание видео (преимущественно горизонтальный формат с допустимой длиной от 5 секунд до 3 часов)


### Целевая аудитория

Месячная аудитория сервиса составляет более 59 млн пользователей [[1]](https://vc.ru/marketing/380331-yandeks-dzen-eto-60-mln-polzovateley-kotorye-gotovy-u-vas-pokupat-pokazyvayu-polzu-dlya-biznesa-v-cifrah#:~:text=%D0%91%D0%BE%D0%BB%D1%8C%D1%88%D0%B0%D1%8F%20%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D1%8F.,%D1%8D%D1%82%D0%BE%20%D1%81%D1%80%D0%B0%D0%B2%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%20%D0%B2%D1%8B%D1%81%D0%BE%D0%BA%D0%B8%D0%B9%20%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%20%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8.)

___

Ежедневная нагрузка по итогам 2021 года составила 22 млн человек [[2]](https://vc.ru/media/412721-22-mln-polzovateley-v-den-i-potencialnye-18-9-mlrd-rubley-vyruchki-v-god-chto-poluchit-vk-posle-pokupki-dzena#:~:text=%D0%9A%20%D0%BA%D0%BE%D0%BD%D1%86%D1%83%202019%20%D0%B3%D0%BE%D0%B4%D0%B0%20%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D0%B0%D1%8F,%2C%20%D0%B2%20%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D1%8E%D1%89%D0%B5%D0%BC%20%E2%80%94%2050%20%D1%82%D1%8B%D1%81%D1%8F%D1%87.)

___

##### С учетом работы сервиса только на территории РФ, наблюдается следующая географическая статистика пользователей сервиса:

- На города Москву и Санкт-Петербург приходится 34% пользователей
- Другие города-миллионники составляют 25% от общего числа пользователей
- Доля пользователей, проживающих в городах с численностью населения более 500 тыс человек и до миллиона - 11%
- Остальные пользователи - 30% - проживают в небольших городах и других населенных пунктах с населением до 500 тыс человек

## 2. Расчет нагрузки <a name="2"></a>

##### Согласно проведенному анализу была получена следующая сводка статистических наблюдений:

1) Каждый пользователь проводит на сервисе более 45 минут в день [[3]](https://vc.ru/marketing/380331-yandeks-dzen-eto-60-mln-polzovateley-kotorye-gotovy-u-vas-pokupat-pokazyvayu-polzu-dlya-biznesa-v-cifrah#:~:text=%D0%9F%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B2%D0%BE%D0%B4%D1%8F%D1%82%20%D0%B2%20%D0%BB%D0%B5%D0%BD%D1%82%D0%B5%20%D0%B1%D0%BE%D0%BB%D1%8C%D1%88%D0%B5%2045%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C%20%E2%80%94%20%D1%8D%D1%82%D0%BE%20%D1%81%D1%80%D0%B0%D0%B2%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%20%D0%B2%D1%8B%D1%81%D0%BE%D0%BA%D0%B8%D0%B9%20%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%20%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8.)
2) В среднем у пользователя уходит до 2 минут на прочтение новостной статьи [[4]](https://vc.ru/marketing/380331-yandeks-dzen-eto-60-mln-polzovateley-kotorye-gotovy-u-vas-pokupat-pokazyvayu-polzu-dlya-biznesa-v-cifrah#:~:text=%D0%9F%D0%B5%D1%80%D0%B5%D0%B4%20%D0%BF%D0%B5%D1%80%D0%B5%D1%85%D0%BE%D0%B4%D0%BE%D0%BC%20%D0%BD%D0%B0%20%D0%BF%D0%BE%D1%81%D0%B0%D0%B4%D0%BE%D1%87%D0%BD%D1%83%D1%8E%20%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%83%20%D1%87%D0%B8%D1%82%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%20%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%BE%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%20%D0%BF%D1%80%D0%BE%D0%B2%D0%BE%D0%B4%D0%B8%D1%82%20%D0%BD%D0%B0%20%D1%81%D1%82%D0%B0%D1%82%D1%8C%D0%B5%20%E2%80%94%20%D0%B2%202021%20%D0%B3%D0%BE%D0%B4%D1%83%20%D1%81%D1%80%D0%B5%D0%B4%D0%BD%D0%B5%D0%B5%20%D0%B2%D1%80%D0%B5%D0%BC%D1%8F%20%D1%87%D1%82%D0%B5%D0%BD%D0%B8%D1%8F%20%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9%20%D1%81%D1%82%D0%B0%D1%82%D1%8C%D0%B8%20%D1%81%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%B8%D0%BB%D0%BE%202%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%D1%8B.)
3) В среднем количество активных блогеров на настоящий момент составляет 45-50 тыс [[5]](https://vc.ru/media/412721-22-mln-polzovateley-v-den-i-potencialnye-18-9-mlrd-rubley-vyruchki-v-god-chto-poluchit-vk-posle-pokupki-dzena#:~:text=%D0%A7%D0%B8%D1%81%D0%BB%D0%BE%20%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85%20%D0%B1%D0%BB%D0%BE%D0%B3%D0%B5%D1%80%D0%BE%D0%B2%20%D0%B2%202020%20%D0%B3%D0%BE%D0%B4%D1%83%20%D0%B4%D0%BE%D1%81%D1%82%D0%B8%D0%B3%D0%BB%D0%BE%2045%20%D1%82%D1%8B%D1%81%D1%8F%D1%87%2C%20%D0%B2%20%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D1%8E%D1%89%D0%B5%D0%BC%20%E2%80%94%2050%20%D1%82%D1%8B%D1%81%D1%8F%D1%87.)
4) У активных блогеров в среднем выходит по 1-2 видео ролику в день для соответствия алгоритмам сервиса [[6]](https://yandex.ru/q/question/s_kakoi_periodichnostiu_nuzhno_delat_v_330b16a2/#:~:text=%D0%9B%D1%83%D1%87%D1%88%D0%B8%D0%B9%20%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82%201%20%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C.)
5) Как было указано выше, ежедневная нагрузка на текущий момент составляет около 22 млн пользователей.
6) Средний размер новостной статьи составляет 3500 символов [[7]](https://text.ru/blog/kak-pisat-posty-v-yandeks-dzen-povyshaem-ohvaty-i-dochityvaniya#:~:text=%D0%9E%D0%BF%D1%82%D0%B8%D0%BC%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9%20%D0%BE%D0%B1%D1%8A%D1%91%D0%BC%20%D1%82%D0%B5%D0%BA%D1%81%D1%82%D0%B0%20%D0%B4%D0%BB%D1%8F%20%D1%81%D1%82%D0%B0%D1%82%D1%8C%D0%B8%20%E2%80%94%202000%2D3000%20%D0%B7%D0%BD%D0%B0%D0%BA%D0%BE%D0%B2%20%D0%B1%D0%B5%D0%B7%20%D0%BF%D1%80%D0%BE%D0%B1%D0%B5%D0%BB%D0%BE%D0%B2.)
7) Пост содержит одно изображение и текст до 1500 символов [[8]](https://text.ru/blog/kak-pisat-posty-v-yandeks-dzen-povyshaem-ohvaty-i-dochityvaniya#:~:text=%D0%A8%D0%B0%D0%B1%D0%BB%D0%BE%D0%BD%20%D0%BF%D0%BE%D1%81%D1%82%D0%B0%20%D0%BD%D0%B5%20%D0%BF%D0%BE%D0%B7%D0%B2%D0%BE%D0%BB%D1%8F%D0%B5%D1%82%20%D0%B0%D0%B2%D1%82%D0%BE%D1%80%D1%83%20%D1%80%D0%B0%D0%B7%D0%BC%D0%B5%D1%81%D1%82%D0%B8%D1%82%D1%8C%20%D1%82%D0%B5%D0%BA%D1%81%D1%82%20%D0%B4%D0%BB%D0%B8%D0%BD%D0%BD%D0%B5%D0%B5%201500%20%D1%81%D0%B8%D0%BC%D0%B2%D0%BE%D0%BB%D0%BE%D0%B2%20%D0%B8%20%D0%B1%D0%BE%D0%BB%D1%8C%D1%88%D0%B5%20%D0%BE%D0%B4%D0%BD%D0%BE%D0%B9%20%D0%BA%D0%B0%D1%80%D1%82%D0%B8%D0%BD%D0%BA%D0%B8.) 
8) В среднем каждый пользователь тратит около 80% времени на просмотр публикаций блогеров [[9]](https://habr.com/ru/news/t/532670/#:~:text=%C2%AB%D0%AF%D0%BD%D0%B4%D0%B5%D0%BA%D1%81.%D0%94%D0%B7%D0%B5%D0%BD%C2%BB%20%D1%80%D0%B0%D1%81%D1%81%D0%BA%D0%B0%D0%B7%D0%B0%D0%BB%2C%20%D1%87%D1%82%D0%BE%20%D0%B2%20%D1%81%D1%80%D0%B5%D0%B4%D0%BD%D0%B5%D0%BC%20%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B2%D0%BE%D0%B4%D1%8F%D1%82%20%D0%BD%D0%B0%20%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5%20%D0%BE%D0%BA%D0%BE%D0%BB%D0%BE%2045%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C%2C%20%D0%BF%D1%80%D0%B8%D1%87%D0%B5%D0%BC%2080%25%20%D1%8D%D1%82%D0%BE%D0%B3%D0%BE%20%D0%B2%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%B8%20%D0%BE%D0%BD%D0%B8%20%D0%B7%D0%BD%D0%B0%D0%BA%D0%BE%D0%BC%D1%8F%D1%82%D1%81%D1%8F%20%D1%81%20%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%D0%BC%D0%B8%20%D0%B1%D0%BB%D0%BE%D0%B3%D0%B5%D1%80%D0%BE%D0%B2.)
9) Статистика по временипрепровождения пользователей: 60% - чтение публикаций, 40% - просмотр видео [[10]](https://habr.com/ru/news/t/532670/#:~:text=%D0%9F%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%2C%20%D1%87%D1%82%D0%BE%2060,%D0%BD%D0%B0%20%D1%87%D1%82%D0%B5%D0%BD%D0%B8%D0%B5%20%D1%81%D1%82%D0%B0%D1%82%D0%B5%D0%B9.)
10) Средняя длина ролика составляет 40 секунд
11) Количество просмотров роликов по данным на конец 2021 года составило более 20 млн просмотров в день [[11]](https://habr.com/ru/news/t/532670/#:~:text=%C2%AB%D0%AF%D0%BD%D0%B4%D0%B5%D0%BA%D1%81.%D0%94%D0%B7%D0%B5%D0%BD%C2%BB%20%D1%80%D0%B0%D1%81%D1%81%D0%BA%D0%B0%D0%B7%D0%B0%D0%BB%2C%20%D1%87%D1%82%D0%BE%20%D0%B2%20%D1%81%D1%80%D0%B5%D0%B4%D0%BD%D0%B5%D0%BC%20%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B2%D0%BE%D0%B4%D1%8F%D1%82%20%D0%BD%D0%B0%20%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5%20%D0%BE%D0%BA%D0%BE%D0%BB%D0%BE%2045%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C%2C%20%D0%BF%D1%80%D0%B8%D1%87%D0%B5%D0%BC%2080%25%20%D1%8D%D1%82%D0%BE%D0%B3%D0%BE%20%D0%B2%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%B8%20%D0%BE%D0%BD%D0%B8%20%D0%B7%D0%BD%D0%B0%D0%BA%D0%BE%D0%BC%D1%8F%D1%82%D1%81%D1%8F%20%D1%81%20%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%D0%BC%D0%B8%20%D0%B1%D0%BB%D0%BE%D0%B3%D0%B5%D1%80%D0%BE%D0%B2.)

___

Используя данную статистику, можем рассчитать нагрузку на сервис:

Итак, мы имеем следующее разделение разделение по типу временипрепровождения пользователей: новостные публикации(1) и публикации блогеров(2).

Согласно приведенной статистике, на публикации блогеров приходится 80%, таким образом на новостные публикации приходится ~20% нагрузки.

Таким образом, можем условно принять:
1) количество пользователей в день, смотрящих только новостной контент, равным 22 000 000 * 0.2 = <ins>4 400 000</ins>
2) количество пользователей в день, смотрящих только публикации блогеров, равным 22 000 000 * 0.8 = <ins>17 600 000</ins>

___

##### Рассчитаем нагрузку, приходящуюся на новостной сервис:

Каждый пользователь, имея среднюю скорость просмотра публикаций 1 request / 120 sec,
нагрузка на новостной сервис будет равна 4 400 000 * 1 request / 120 sec = ~<ins>37 000 rps</ins>

___

##### Рассчитаем нагрузку, приходящуюся на сервис контента блогеров:

Согласно статистике, пользователь, просматривающий контент блогеров, тратит 60% времени на публикации и 40% времени на просмотр видео.

Таким образом, можем условно принять:
1) количество пользователей в день, смотрящих только публикации блогеров, равным 17 600 000 * 0.6 = <ins>10 560 000</ins>
2) количество пользователей в день, смотрящих только ролики блогеров, равным 17 600 000 * 0.3 = <ins>5 280 000</ins>
3) количество пользователей в день, смотрящих только видео блогеров, равным 17 600 000 * 0.1 = <ins>1 760 000</ins>

Теперь можем рассчитать отдельно нагрузку на сервис публикаций, сервис роликов и сервис видео.

___

##### Рассчитаем нагрузку, приходящуюся на сервис публикаций блогеров:

Скорость просмотра публикаций пользователем примем равной 1 request / 30 sec.

Тогда нагрузка на сервис публикаций блогеров будет равна 10 560 000 * 1 request / 30 sec = ~<ins>352 000 rps</ins>

___

##### Рассчитаем нагрузку, приходящуюся на сервис роликов блогеров:

Среднее время просмотра ролика равно 40 sec, тогда скорость просмотра публикаций пользователем примем равной 1 request / 40 sec.

Тогда нагрузка на сервис публикаций блогеров будет равна 5 280 000 * 1 request / 40 sec = ~<ins>132 000 rps</ins>

___

##### Рассчитаем нагрузку, приходящуюся на сервис видео блогеров:

Скорость просмотра публикаций пользователем примем равной 1 request / 180 sec.

Тогда нагрузка на сервис публикаций блогеров будет равна 1 760 000 * 1 request / 180 sec = ~<ins>10 000 rps</ins>

___


## 3. Логическая схема <a name="3"></a>

## 4. Физическая схема <a name="4"></a>

## 5. Технологии <a name="5"></a>

## 6. Схема проекта <a name="6"></a>

## 7. Список серверов <a name="7"></a>

## 8. Список использованных источников <a name="8"></a>
