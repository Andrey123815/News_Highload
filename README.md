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
- просмотр и создание новостных статей (текст, изображения, видео)
- просмотр и создание постов (1,5 тысячи знаков с картинками не больше 10 штук)
- просмотре и создание роликов (видео продолжительностью до 1 минуты)
- просмотр и создание видео (преимущественно горизонтальный формат с допустимой длиной до 3 часов)

### Целевая аудитория

Месячная аудитория сервиса составляет более 59 млн пользователей [[1]](https://vc.ru/marketing/380331-yandeks-dzen-eto-60-mln-polzovateley-kotorye-gotovy-u-vas-pokupat-pokazyvayu-polzu-dlya-biznesa-v-cifrah#:~:text=%D0%91%D0%BE%D0%BB%D1%8C%D1%88%D0%B0%D1%8F%20%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D1%8F.,%D1%8D%D1%82%D0%BE%20%D1%81%D1%80%D0%B0%D0%B2%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%20%D0%B2%D1%8B%D1%81%D0%BE%D0%BA%D0%B8%D0%B9%20%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%20%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8.)

___

Ежедневная нагрузка по итогам 2021 года составила 22 млн человек [[2]](https://vc.ru/media/412721-22-mln-polzovateley-v-den-i-potencialnye-18-9-mlrd-rubley-vyruchki-v-god-chto-poluchit-vk-posle-pokupki-dzena#:~:text=%D0%9A%20%D0%BA%D0%BE%D0%BD%D1%86%D1%83%202019%20%D0%B3%D0%BE%D0%B4%D0%B0%20%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D0%B0%D1%8F,%2C%20%D0%B2%20%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D1%8E%D1%89%D0%B5%D0%BC%20%E2%80%94%2050%20%D1%82%D1%8B%D1%81%D1%8F%D1%87.)

___

##### С учетом работы сервиса только на территории РФ, наблюдается следующая географическая статистика пользователей сервиса по данным, предоставленным на vc.ru [[3]](https://vc.ru/marketing/380331-yandeks-dzen-eto-60-mln-polzovateley-kotorye-gotovy-u-vas-pokupat-pokazyvayu-polzu-dlya-biznesa-v-cifrah#:~:text=%D0%92%20%D0%BA%D0%B0%D1%80%D1%83%D1%81%D0%B5%D0%BB%D0%B8%20%E2%80%94%20%D1%81%D1%80%D0%B5%D0%B7%D1%8B%20%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B8%20%D0%94%D0%B7%D0%B5%D0%BD%D0%B0%20%D0%BF%D0%BE%20%D0%B3%D0%B5%D0%BE%2C%20%D0%BF%D0%BE%D0%BB%D1%83%2C%20%D0%B2%D0%BE%D0%B7%D1%80%D0%B0%D1%81%D1%82%D1%83%20%D0%B8%20%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0%D0%BC.):

- На города Москву и Санкт-Петербург приходится 34% пользователей
- Другие города-миллионники составляют 25% от общего числа пользователей
- Доля пользователей, проживающих в городах с численностью населения более 500 тыс человек и до миллиона - 11%
- Остальные пользователи - 30% - проживают в небольших городах и других населенных пунктах с населением до 500 тыс человек

## 2. Расчет нагрузки <a name="2"></a>

##### Согласно проведенному анализу была получена следующая сводка статистических наблюдений:

1) Каждый пользователь проводит на сервисе более 45 минут в день [[4]](https://vc.ru/marketing/380331-yandeks-dzen-eto-60-mln-polzovateley-kotorye-gotovy-u-vas-pokupat-pokazyvayu-polzu-dlya-biznesa-v-cifrah#:~:text=%D0%9F%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B2%D0%BE%D0%B4%D1%8F%D1%82%20%D0%B2%20%D0%BB%D0%B5%D0%BD%D1%82%D0%B5%20%D0%B1%D0%BE%D0%BB%D1%8C%D1%88%D0%B5%2045%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C%20%E2%80%94%20%D1%8D%D1%82%D0%BE%20%D1%81%D1%80%D0%B0%D0%B2%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%20%D0%B2%D1%8B%D1%81%D0%BE%D0%BA%D0%B8%D0%B9%20%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%20%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8.)
2) В среднем у пользователя уходит до 2 минут на прочтение новостной статьи [[5]](https://vc.ru/marketing/380331-yandeks-dzen-eto-60-mln-polzovateley-kotorye-gotovy-u-vas-pokupat-pokazyvayu-polzu-dlya-biznesa-v-cifrah#:~:text=%D0%9F%D0%B5%D1%80%D0%B5%D0%B4%20%D0%BF%D0%B5%D1%80%D0%B5%D1%85%D0%BE%D0%B4%D0%BE%D0%BC%20%D0%BD%D0%B0%20%D0%BF%D0%BE%D1%81%D0%B0%D0%B4%D0%BE%D1%87%D0%BD%D1%83%D1%8E%20%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%83%20%D1%87%D0%B8%D1%82%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%20%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%BE%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%20%D0%BF%D1%80%D0%BE%D0%B2%D0%BE%D0%B4%D0%B8%D1%82%20%D0%BD%D0%B0%20%D1%81%D1%82%D0%B0%D1%82%D1%8C%D0%B5%20%E2%80%94%20%D0%B2%202021%20%D0%B3%D0%BE%D0%B4%D1%83%20%D1%81%D1%80%D0%B5%D0%B4%D0%BD%D0%B5%D0%B5%20%D0%B2%D1%80%D0%B5%D0%BC%D1%8F%20%D1%87%D1%82%D0%B5%D0%BD%D0%B8%D1%8F%20%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9%20%D1%81%D1%82%D0%B0%D1%82%D1%8C%D0%B8%20%D1%81%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%B8%D0%BB%D0%BE%202%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%D1%8B.)
3) В среднем количество активных блогеров на настоящий момент составляет 45-50 тыс [[6]](https://vc.ru/media/412721-22-mln-polzovateley-v-den-i-potencialnye-18-9-mlrd-rubley-vyruchki-v-god-chto-poluchit-vk-posle-pokupki-dzena#:~:text=%D0%A7%D0%B8%D1%81%D0%BB%D0%BE%20%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85%20%D0%B1%D0%BB%D0%BE%D0%B3%D0%B5%D1%80%D0%BE%D0%B2%20%D0%B2%202020%20%D0%B3%D0%BE%D0%B4%D1%83%20%D0%B4%D0%BE%D1%81%D1%82%D0%B8%D0%B3%D0%BB%D0%BE%2045%20%D1%82%D1%8B%D1%81%D1%8F%D1%87%2C%20%D0%B2%20%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D1%8E%D1%89%D0%B5%D0%BC%20%E2%80%94%2050%20%D1%82%D1%8B%D1%81%D1%8F%D1%87.)
4) У активных блогеров в Яндекс Дзене в среднем выходит по 1-2 ролику в день: поиск осуществлялся на форумах и в комментариях опытных пользователей, 
так как официально подтвержденной цифры нет. Аналогичные сведения имеются и о популярных схожих сервисах - TikTok, Instagram и других.
[[7]](https://yandex.ru/q/question/s_kakoi_periodichnostiu_nuzhno_delat_v_330b16a2/#:~:text=%D0%98%D0%B7%20%D0%BB%D0%B8%D1%87%D0%BD%D0%BE%D0%B3%D0%BE%20%D0%BE%D0%BF%D1%8B%D1%82%D0%B0%20%D0%BC%D0%BE%D0%B3%D1%83%20%D1%81%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D1%8C%2C%20%D1%87%D1%82%D0%BE%20%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D1%82%D0%BE%D1%87%D0%BD%D0%BE%20%D0%BE%D0%B4%D0%BD%D0%BE%D0%B9%2D%D0%B4%D0%B2%D1%83%D1%85%20%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B9%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C%20%2D%20%D0%B2%D1%81%D0%B5%20%D0%B7%D0%B0%D0%B2%D0%B8%D1%81%D0%B8%D1%82%20%D0%BE%D1%82%20%D1%82%D0%BE%D0%B3%D0%BE%2C%20%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%BE%20%D0%B2%D1%8B%20%D1%85%D0%BE%D1%82%D0%B8%D1%82%D0%B5%20%D0%B7%D0%B0%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D1%82%D1%8C.),
[[8]](https://yandex.ru/q/question/s_kakoi_periodichnostiu_nuzhno_delat_v_330b16a2/#:~:text=%D0%A0%D0%B0%D1%81%D1%81%D0%BC%D0%BE%D1%82%D1%80%D1%8E%20%D1%82%D1%80%D0%B8%20%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82%D0%B0),
[[9]](https://yandex.ru/q/question/s_kakoi_periodichnostiu_nuzhno_delat_v_330b16a2/#:~:text=%D0%9B%D1%83%D1%87%D1%88%D0%B8%D0%B9%20%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82%201%20%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C.),
[[10]](https://tiktokeri.ru/prodvizhenie/kak-chasto-postit-v-tik-tok#:~:text=%D0%90%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B9%20%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%20%D0%B2%20%D1%81%D1%80%D0%B5%D0%B4%D0%BD%D0%B5%D0%BC%20%D0%BF%D0%BE%D1%81%D1%82%D0%B8%D1%82%201%2D2%20%D1%80%D0%BE%D0%BB%D0%B8%D0%BA%D0%B0%20%D0%B2%20%D1%81%D0%BE%D1%86%D1%81%D0%B5%D1%82%D0%B8%20%D0%B5%D0%B6%D0%B5%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D0%BE.%20%D0%AD%D1%82%D0%BE%20%D1%81%D0%BA%D0%B0%D0%B7%D1%8B%D0%B2%D0%B0%D0%B5%D1%82%D1%81%D1%8F%20%D0%BD%D0%B0%20%D0%BF%D1%80%D0%BE%D0%B4%D0%B2%D0%B8%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8%20%E2%80%94%20%D0%B2%D0%B8%D0%B4%D0%B5%D0%BE%D1%80%D0%BE%D0%BB%D0%B8%D0%BA%D0%B8%20%D0%B6%D0%B4%D1%83%D1%82%20%D0%BF%D0%BE%D1%81%D1%82%D0%BE%D1%8F%D0%BD%D0%BD%D0%BE%2C%20%D0%BD%D0%B0%20%D0%BD%D0%B8%D1%85%20%D1%80%D0%B5%D0%B0%D0%B3%D0%B8%D1%80%D1%83%D1%8E%D1%82%2C%20%D0%B2%D0%B0%D1%81%20%D0%BD%D0%B5%20%D0%B7%D0%B0%D0%B1%D1%8B%D0%B2%D0%B0%D1%8E%D1%82%20%D0%BF%D0%BE%D0%B4%D0%BF%D0%B8%D1%81%D1%87%D0%B8%D0%BA%D0%B8.)
5) У активных блогеров в среднем выходит по 1-2 поста в день
(берем на примере Instagram - третьей по поулярности соцсети в РФ, из чего следует возможность полагаться на данную статистику)
[[11]](https://smmplanner.com/blog/pravila-publikacii-kontenta-kogda-i-skolko/#:~:text=Popsters%20%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D0%BB%20%D0%B8%D1%81%D1%81%D0%BB%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B8%20%D0%B2%202019%20%D0%B3%D0%BE%D0%B4%D1%83%20%D0%B8%20%D0%B2%D1%8B%D1%8F%D1%81%D0%BD%D0%B8%D0%BB%2C%20%D1%87%D1%82%D0%BE%20%D0%B2%20%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D0%BE%D0%BC%20%D0%BF%D0%BE%20%D0%B4%D0%B2%D0%B0%20%D0%BF%D0%BE%D1%81%D1%82%D0%B0%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C%20%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D1%83%D1%8E%D1%82%20%D0%98%D0%BD%D1%81%D1%82%D0%B0%D0%B3%D1%80%D0%B0%D0%BC*%2D%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D1%8B%20%D1%81%20%D0%BF%D0%BE%D0%B4%D0%BF%D0%B8%D1%81%D1%87%D0%B8%D0%BA%D0%B0%D0%BC%D0%B8%20%D0%BE%D1%82%20100%20%D1%82%D1%8B%D1%81%D1%8F%D1%87%2C%20%D0%B0%20%D0%BE%D0%B4%D0%B8%D0%BD%20%E2%80%93%20%D0%BC%D0%B5%D0%BD%D0%B5%D0%B5%20100%20%D1%82%D1%8B%D1%81%D1%8F%D1%87.%20%D0%92%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C%20%D0%BD%D0%B0%20%D0%BF%D0%BE%D1%81%D1%82%20%D0%BF%D1%80%D0%B8%20%D1%8D%D1%82%D0%BE%D0%BC%20%D0%BE%D0%B4%D0%B8%D0%BD%D0%B0%D0%BA%D0%BE%D0%B2%D0%B0%D1%8F%20%D0%B4%D0%BB%D1%8F%20%D0%B2%D1%81%D0%B5%D1%85%20%D1%82%D0%B8%D0%BF%D0%BE%D0%B2%20%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%BE%D0%B2%20%E2%80%93%20%D1%81%D0%BA%D0%B0%D0%B7%D1%8B%D0%B2%D0%B0%D0%B5%D1%82%D1%81%D1%8F%20%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%B0%D1%8F%20%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B0%20%D1%81%D0%BE%D1%86%D1%81%D0%B5%D1%82%D0%B8.)
6) Как было указано выше, ежедневная нагрузка на текущий момент составляет более 22 млн пользователей. 
7) Средний размер новостной статьи составляет 3000 символов [[12]](https://text.ru/blog/kak-pisat-posty-v-yandeks-dzen-povyshaem-ohvaty-i-dochityvaniya#:~:text=%D0%9E%D0%BF%D1%82%D0%B8%D0%BC%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9%20%D0%BE%D0%B1%D1%8A%D1%91%D0%BC%20%D1%82%D0%B5%D0%BA%D1%81%D1%82%D0%B0%20%D0%B4%D0%BB%D1%8F%20%D1%81%D1%82%D0%B0%D1%82%D1%8C%D0%B8%20%E2%80%94%202000%2D3000%20%D0%B7%D0%BD%D0%B0%D0%BA%D0%BE%D0%B2%20%D0%B1%D0%B5%D0%B7%20%D0%BF%D1%80%D0%BE%D0%B1%D0%B5%D0%BB%D0%BE%D0%B2.)
8) Пост содержит до 10 изображений и текст до 1500 символов [[13]](https://dzen.ru/help/mobile/post.html#:~:text=%D0%9E%D0%B1%D1%8A%D0%B5%D0%BC%20%D0%BF%D0%BE%D1%81%D1%82%D0%B0%C2%A0%E2%80%94%201%2C5%C2%A0%D1%82%D1%8B%D1%81%D1%8F%D1%87%D0%B8%20%D0%B7%D0%BD%D0%B0%D0%BA%D0%BE%D0%B2%20%D1%81%20%D0%BA%D0%B0%D1%80%D1%82%D0%B8%D0%BD%D0%BA%D0%B0%D0%BC%D0%B8%20%D0%BD%D0%B5%20%D0%B1%D0%BE%D0%BB%D1%8C%D1%88%D0%B5%2010%C2%A0%D1%88%D1%82%D1%83%D0%BA.) 
9) В среднем каждый пользователь тратит около 80% времени на просмотр публикаций блогеров [[14]](https://habr.com/ru/news/t/532670/#:~:text=%C2%AB%D0%AF%D0%BD%D0%B4%D0%B5%D0%BA%D1%81.%D0%94%D0%B7%D0%B5%D0%BD%C2%BB%20%D1%80%D0%B0%D1%81%D1%81%D0%BA%D0%B0%D0%B7%D0%B0%D0%BB%2C%20%D1%87%D1%82%D0%BE%20%D0%B2%20%D1%81%D1%80%D0%B5%D0%B4%D0%BD%D0%B5%D0%BC%20%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B2%D0%BE%D0%B4%D1%8F%D1%82%20%D0%BD%D0%B0%20%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5%20%D0%BE%D0%BA%D0%BE%D0%BB%D0%BE%2045%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C%2C%20%D0%BF%D1%80%D0%B8%D1%87%D0%B5%D0%BC%2080%25%20%D1%8D%D1%82%D0%BE%D0%B3%D0%BE%20%D0%B2%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%B8%20%D0%BE%D0%BD%D0%B8%20%D0%B7%D0%BD%D0%B0%D0%BA%D0%BE%D0%BC%D1%8F%D1%82%D1%81%D1%8F%20%D1%81%20%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%D0%BC%D0%B8%20%D0%B1%D0%BB%D0%BE%D0%B3%D0%B5%D1%80%D0%BE%D0%B2.)
10) Статистика по временипрепровождению пользователей: 60% - чтение публикаций, 40% - просмотр видео [[15]](https://habr.com/ru/news/t/532670/#:~:text=%D0%9F%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%2C%20%D1%87%D1%82%D0%BE%2060,%D0%BD%D0%B0%20%D1%87%D1%82%D0%B5%D0%BD%D0%B8%D0%B5%20%D1%81%D1%82%D0%B0%D1%82%D0%B5%D0%B9.)
11) Средняя длина ролика по официально неподтвержденным данным составляет 40 секунд
12) Количество просмотров роликов по данным на конец 2021 года составило более 20 млн просмотров в день [[16]](https://habr.com/ru/news/t/532670/#:~:text=%C2%AB%D0%AF%D0%BD%D0%B4%D0%B5%D0%BA%D1%81.%D0%94%D0%B7%D0%B5%D0%BD%C2%BB%20%D1%80%D0%B0%D1%81%D1%81%D0%BA%D0%B0%D0%B7%D0%B0%D0%BB%2C%20%D1%87%D1%82%D0%BE%20%D0%B2%20%D1%81%D1%80%D0%B5%D0%B4%D0%BD%D0%B5%D0%BC%20%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B2%D0%BE%D0%B4%D1%8F%D1%82%20%D0%BD%D0%B0%20%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5%20%D0%BE%D0%BA%D0%BE%D0%BB%D0%BE%2045%20%D0%BC%D0%B8%D0%BD%D1%83%D1%82%20%D0%B2%20%D0%B4%D0%B5%D0%BD%D1%8C%2C%20%D0%BF%D1%80%D0%B8%D1%87%D0%B5%D0%BC%2080%25%20%D1%8D%D1%82%D0%BE%D0%B3%D0%BE%20%D0%B2%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%B8%20%D0%BE%D0%BD%D0%B8%20%D0%B7%D0%BD%D0%B0%D0%BA%D0%BE%D0%BC%D1%8F%D1%82%D1%81%D1%8F%20%D1%81%20%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%D0%BC%D0%B8%20%D0%B1%D0%BB%D0%BE%D0%B3%D0%B5%D1%80%D0%BE%D0%B2.)
13) Предполагаем, что активный блогер выкладывает по 3 видео в месяц
___

Используя данную статистику, можем рассчитать нагрузку на сервис:

Мы имеем следующее разделение разделение по типу временипрепровождения пользователей: новостные публикации(1) и публикации блогеров(2).

Согласно приведенной статистике, на публикации блогеров приходится 80%, таким образом на новостные публикации приходится ~20% временипрепровождения пользователей.

```
Пояснение к упрощению модели
----------------------------
Текущую модель можно упростить. 
Равноправность такой замены можно доказать на следующем примере:
Пусть 
    n - количество пользователей сервиса в день, 
    t - время их наждения на сервисе,
Тогда, с учетом выше представленных статистик,
    суммарное количество времени, затрачиваемое пользователями на просмотр новостей, равно n * (0.2 * t);
    суммарное количество времени, затрачиваемое пользователями на просмотр публикаций блогеров, равно n * (0.8 * t);
Что эквивалентно модели, где
    (0.2 * n) пользователей проводят все свое время на сервисе (t) только за просмотром новостей и
    (0.8 * n) пользователей проводят все свое время на сервисе (t) только за просмотром публикаций блогеров
```

Таким образом, можем условно принять (согласно подходу упрощенной модели):
1) количество пользователей в день, смотрящих только новостной контент, равным 22 000 000 * 0.2 = <ins>4 400 000</ins>
2) количество пользователей в день, смотрящих только публикации блогеров, равным 22 000 000 * 0.8 = <ins>17 600 000</ins>

___

##### Рассчитаем нагрузку, приходящуюся на новостной сервис:

Пользователи, имея среднюю скорость просмотра публикаций 1 request / 120 sec в период пребывания на сервисе (в среднем 45 минут / день).

Большинство сервисов не грузит по одной новости на request, а прогружает по 10-100 постов сразу и кеширует их. 
Таким образом, клиент, сделав один-два запроса, получает нужное количество новостей на сеанс. 
Примем количество сеансов в день каждого пользователя равным 5. Таким образом количество запросов в день будет равно ~10 request / day.

В результате просмотр новостного контента пользователями создает нагрузку, равную 
4 400 000 * 10 request / (24 * 60 * 60) sec = ~<ins>510 rps</ins>

В день публикуется ~3000 новостных постов (согласно статистике, представленной выше), тогда нагрузка на создание новостей составит
3 000 request / day = 3 000 request / (24 * 60 * 60) sec = ~<ins>0.05 rps</ins>

___

##### Рассчитаем нагрузку, приходящуюся на сервис контента блогеров:

Согласно статистике, пользователь, просматривающий контент блогеров, тратит 60% времени на публикации и 40% времени на просмотр видео.

Таким образом, можем условно принять (согласно подходу упрощенной модели):
1) количество пользователей в день, смотрящих только публикации блогеров, равным 17 600 000 * 0.6 = <ins>10 560 000</ins>
2) количество пользователей в день, смотрящих только ролики блогеров, равным 17 600 000 * 0.3 = <ins>5 280 000</ins>
3) количество пользователей в день, смотрящих только видео блогеров, равным 17 600 000 * 0.1 = <ins>1 760 000</ins>

Теперь можем рассчитать отдельно нагрузку на сервис публикаций, сервис роликов и сервис видео.

___

##### Рассчитаем нагрузку, приходящуюся на сервис публикаций блогеров:

Скорость просмотра публикаций пользователем примем равной 
1 request / 30 sec в период пребывания на сервисе (в среднем 45 минут / день).

Как было указано в прошлом разделе, сервисы загружают посты по 100 за один request.
Таким образом на один сеанс точно хватит одного запроса. 
Однако количество сеансов пользователя в день, как было указано выше, принимаем за 5.
Таким образом, количество запросов в день будет равно 5.

В результате просмотр публикаций блогеров создает нагрузку, равную
10 560 000 * 5 request / (24 * 60 * 60 сек) = ~<ins>700 rps</ins>

В день активными блогерами (согласно статистике на 2022 год число блогеров составило 50 000 пользователей) публикуется 1-2 поста (согласно статистике, представленной выше), тогда нагрузка на создание новостей составит
50 000 блогеров * 2 request / (24 * 60 * 60) sec = ~<ins>1.2 rps</ins>

___

##### Рассчитаем нагрузку, приходящуюся на сервис роликов блогеров:

Среднее время просмотра ролика равно 40 sec, тогда скорость просмотра публикаций пользователем примем равной 
1 request / 40 sec в период пребывания на сервисе (в среднем 45 минут / день).

Пусть за один запрос загружается 5 роликов.

В результате просмотр роликов блогеров создает нагрузку, равную
5 280 000 * 1 request / 40 sec * 45 мин / (24 * 60 мин) / 5 = ~<ins>825 rps</ins>

В день активными блогерами публикуется 1-2 ролика (согласно статистике, представленной выше), тогда нагрузка на загрузку новых роликов составит
50 000 блогеров * 2 request / (24 * 60 * 60) sec = ~<ins>1.2 rps</ins>

___

##### Рассчитаем нагрузку, приходящуюся на сервис видео блогеров:

Скорость просмотра видео каждым пользователем примем равной 
1 request / 1800 sec в период пребывания на сервисе (в среднем 45 минут / день).

В результате просмотр видео блогеров создает нагрузку, равную 
1 760 000 * 1 request / 1800 sec * 45 мин / (24 * 60 мин) = ~<ins>32 rps</ins>

Как было указано выше, предполагаем, что блогер выкладывает 2-3 видео в месяц. Тогда нагрузка на загрузку новых видео составит
50 000 блогеров * 3 request / (30 * 24 * 60 * 60) sec = ~<ins>0.06 rps</ins>

___

#### Итоговая нагрузка на сервис с разделением по типам запросов

| **Тип нагрузки**            | **Количество запросов в секунду** |
|-----------------------------|-----------------------------------| 
| Получение новостей          | 510 rps                           |
| Создание новостей           | 0.05 rps                          |
| Получение постов  блогеров  | 700 rps                           |
| Создание постов  блогеров   | 1.2 rps                           |
| Получение роликов блогеров  | 825 rps                           |
| Создание роликов блогеров   | 1.2 rps                           |
| Получение видео блогеров    | 32 rps                            |
| Создание видео блогеров     | 0.06 rps                          |
| Суммарная нагрузка          | 2 070 rps                         |

___

### Расчет статического размера хранилища:

Рассчитаем статический размер хранилища, которые должно быть в распоряжении сервиса по итогам прошлых лет:

- Новостной сервис каждый день публикует до 3 000 публикаций (берем количество новостей равное количеству выпускаемых новостей в день 
агенством ТАСС [[17]](https://tass.ru/tass-today#:~:text=%D0%95%D0%B6%D0%B5%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D0%BE%20%D0%A2%D0%90%D0%A1%D0%A1%20%D0%B2%D1%8B%D0%BF%D1%83%D1%81%D0%BA%D0%B0%D0%B5%D1%82%20%D0%BE%D0%BA%D0%BE%D0%BB%D0%BE%203%20%D1%82%D1%8B%D1%81.%20%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D0%B9%20%D0%B8%20%D0%BF%D0%BE%D1%80%D1%8F%D0%B4%D0%BA%D0%B0%20600%2D800%20%D1%84%D0%BE%D1%82%D0%BE%2D%20%D0%B8%20%D0%B2%D0%B8%D0%B4%D0%B5%D0%BE%D0%BC%D0%B0%D1%82%D0%B5%D1%80%D0%B8%D0%B0%D0%BB%D0%BE%D0%B2%20%D0%BE%D1%82%20%D1%81%D0%BE%D0%B1%D1%81%D1%82%D0%B2%D0%B5%D0%BD%D0%BD%D1%8B%D1%85%20%D0%BA%D0%BE%D1%80%D1%80%D0%B5%D1%81%D0%BF%D0%BE%D0%BD%D0%B4%D0%B5%D0%BD%D1%82%D0%BE%D0%B2%20%D0%B2%20%D0%A0%D0%BE%D1%81%D1%81%D0%B8%D0%B8%20%D0%B8%20%D0%B7%D0%B0%20%D1%80%D1%83%D0%B1%D0%B5%D0%B6%D0%BE%D0%BC%2C%20%D1%84%D0%BE%D1%80%D0%BC%D0%B8%D1%80%D1%83%D1%8F%20%D1%86%D0%B5%D0%BB%D0%BE%D1%81%D1%82%D0%BD%D1%83%D1%8E%20%D0%B8%20%D0%BE%D0%B1%D1%8A%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%83%D1%8E%20%D0%BA%D0%B0%D1%80%D1%82%D0%B8%D0%BD%D1%83%20%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9.)
- использовать статистику ТАСС можно, так как оно является ведущим новостным агенством в России и имеет самые высокие показатели в этой сфере),
содержащих фото- и видео-материалы, а также текст (~3000 символов)

    Размер хранилища будет определяться сроком хранения старых новостей, который примем равным 1.5 месяцам (90 дней).</br>

    Рассчитаем суммарный вес постов, выкладываемых за один день, опираясь на статистику ТАСС[[18]](https://tass.ru/tass-today#:~:text=%D0%95%D0%B6%D0%B5%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D0%BE%20%D0%A2%D0%90%D0%A1%D0%A1%20%D0%B2%D1%8B%D0%BF%D1%83%D1%81%D0%BA%D0%B0%D0%B5%D1%82%20%D0%BE%D0%BA%D0%BE%D0%BB%D0%BE%203%20%D1%82%D1%8B%D1%81.%20%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D0%B9%20%D0%B8%20%D0%BF%D0%BE%D1%80%D1%8F%D0%B4%D0%BA%D0%B0%20600%2D800%20%D1%84%D0%BE%D1%82%D0%BE%2D%20%D0%B8%20%D0%B2%D0%B8%D0%B4%D0%B5%D0%BE%D0%BC%D0%B0%D1%82%D0%B5%D1%80%D0%B8%D0%B0%D0%BB%D0%BE%D0%B2%20%D0%BE%D1%82%20%D1%81%D0%BE%D0%B1%D1%81%D1%82%D0%B2%D0%B5%D0%BD%D0%BD%D1%8B%D1%85%20%D0%BA%D0%BE%D1%80%D1%80%D0%B5%D1%81%D0%BF%D0%BE%D0%BD%D0%B4%D0%B5%D0%BD%D1%82%D0%BE%D0%B2%20%D0%B2%20%D0%A0%D0%BE%D1%81%D1%81%D0%B8%D0%B8%20%D0%B8%20%D0%B7%D0%B0%20%D1%80%D1%83%D0%B1%D0%B5%D0%B6%D0%BE%D0%BC%2C%20%D1%84%D0%BE%D1%80%D0%BC%D0%B8%D1%80%D1%83%D1%8F%20%D1%86%D0%B5%D0%BB%D0%BE%D1%81%D1%82%D0%BD%D1%83%D1%8E%20%D0%B8%20%D0%BE%D0%B1%D1%8A%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%83%D1%8E%20%D0%BA%D0%B0%D1%80%D1%82%D0%B8%D0%BD%D1%83%20%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9.):
        По статистике, в день выкладывается 3000 текстовых постов, содержащих ~600-800 фото- и видеоматериалов.</br>

| **Тип контента**      | **Количество**          | **Вес одного элемента**               | **Суммарный вес контента**    |
|-----------------------|-------------------------|---------------------------------------|-------------------------------| 
| Текст                 | 3000                    | 3 Кб                                  | 3000 * 3 Кб = 9 Мб            |
| Фото                  | 600                     | 2 Мб                                  | 600 * 2 Мб = 1200 Мб = 1.2 Гб |
| Видео                 | 200                     | 1 мин видео при качестве 720p ~ 20 Мб | 200 * 20 Мб = 4000 Мб = 4 Гб  |
    
  Таким образом размер хранилища должен быть не менее 90 дней * (9 Мб + 1.2 Гб + 4 Гб) / день = ~<ins>0.5 Тб</ins>

- Сервис роликов появился с 2020 года, среднее число блогеров за период 2020 - 2022 составил 50 000 пользователей.
    Примем, что пользователь выкладывает в среднем 1 ролик в день.
    Таким образом размер хранилища должен составлять не менее 3 * 365 дней * 50 000 пользователей * 1 ролик/день * 100Мб/ролик = ~<ins>5.4 Пб</ins>
- Сервис постов существует с 2017 года, среднее число блогеров за этот период составляет 40 000 пользователей.
    Примем, что пользователь выкладывает в среднем 1 пост в день. 
    Тогда, принимая средний вес поста равным 8Мб, размер хранилища должен быть не менее 5 * 365 дней * 40 000 пользователей * 1 пост/день * 8Мб/пост = ~<ins>0.6 Пб</ins> 
- Сервис видео существует с 2020 года, среднее число блогеров за этот период составляет 50 000 пользователей.
    Примем, что блогер выкладывает в среднем 3 видео раз в месяц.
    Тогда, принимая средний вес видео равным 2.8 Гб, размер хранилища должен быть не менее 3 * 365 дней * 50 000 пользователей * 3 видео/ 30 дней * 2.8Гб/видео = ~<ins>15 Пб</ins>

___

### Расчет динамического прироста размера хранилища:

Для рассчета динамического размера хранилища рассмотрим рост нагрузки на наши сервисы.

- Новостной сервис: рост количества новостных постов отсутсвует. Это обсуловлено тем, что 
новостной сервис не является агрегатором новостей из других сервисов, а сам создает публикации, 
количество которых в единицу всегда приблизительно одинаковое. Но условно можем назначить 
динамический прирост равным <ins>0.1 Тб/год</ins> для покрытия всех возможных вариантов роста новостных публикаций.
- Сервис роликов: с 2020 года рост блогеров был в средующей прогрессии: 20 000(2020), 45 000(2021), 50 000(2022). 
Заметим, что пик прироста пользователей был пройден, так как показатели прироста резко уменьшились - в 5 раз. 
Таким образом, можем считать, что приток пользователей будет стабильным и меньше или равным притоку за последний год.
Однако установим коэффициент запаса Кзап, равный 2, для покрытия возможных вариантов варьирования прироста. 
Таким образом, прирост в год будет равен (50 000 - 45 000) * Кзап = 5 000 * 2 = <ins>10 000 блогеров/год</ins>
Таким образом прирост составит (365 дней * 10 000 пользователей * 1 ролик/день * 100Мб/ролик) / год = ~<ins>0.4 Пб/год</ins>
- Сервис постов: как уже было посчитано выше, средний прирост блогеров в год составляет 10 000 пользователей.
Тогда, динамический прирост размера хранилища должен быть не менее 
(365 дней * 10 000 пользователей * 1 пост/день * 8Мб/пост) / год = ~<ins>0.03 Пб/год</ins>
- Сервис видео: динамический прирост размера хранилища с учетом рассчитаного прироста блогеров в год 
должен быть не менее (365 дней * 10 000 пользователей * 1 видео/ 30 дней * 2.8Гб/видео) / год = ~<ins>0.35 Пб/год</ins>

___

### Суммарный размер хранилища

Согласно расчетам:
- Суммарный статический размер хранилища должен быть не менее 0.5Тб + 5.4Пб + 0.6Пб + 5Пб = <ins>15.5 Пб</ins>
- Суммарный динамический прирост размера хранилища должен быть не менее 0.1 Тб/год + 0.4 Пб/год + 0.03 Пб/год + 0.35 Пб/год = <ins>0.8 Пб/год</ins>

Тогда суммарный размер хранилища на настоящий момент должен быть не менее: <br/>
[ Суммарный статический размер хранилища + 1 год * Суммарный динамический прирост размера хранилища / год ] = 15.5 Пб + 1 год * 0.8 Пб/год = <ins>0.8 Пб/год</ins>

Как уже было посчитано выше, прогнозируемый прирост хранилища в год равен 0.8 Пб/год.
___

## 3. Логическая схема <a name="3"></a>

## 4. Физическая схема <a name="4"></a>

## 5. Технологии <a name="5"></a>

## 6. Схема проекта <a name="6"></a>

## 7. Список серверов <a name="7"></a>

## 8. Список использованных источников <a name="8"></a>
