Необходимо сверстать макет страницы интернет-магазина:

https://www.figma.com/file/6LxPDEsauEGanhR2nDW68X/Banki.shop?node-id=0%3A1

###Технические требования:
- при выполнении тестового задания использовать VueJS (без использования Vue CLI)
 - можно использовать Bootstrap, jQuery
  - верстка должна максимально соответствовать предоставленному макету и ui-киту, адаптивная. Желательно PixelPerfect.
  - результат должен корректно отображаться во всех популярных браузерах, включая IE 11 версии
  - при работе над заданием обязательно использование средств автоматизации (webpack или gulp). Конфигурация должна корректно работать на 16 версии Node.js

###Требования к приложению - реализовать следущий функционал:

1. Строка поиска
   При ввода текста в строке поиска должен происходить поиск по названиям позиций.
   Лишние карточки должны исчезать/скрываться.

2. Кнопка "купить"
   При нажатии на кнопку:
   - она должна менять состояние, на 2 сек, на "обрабатывается"
   - после "обрабатывается" переходить в состояние "в корзине"
     Отображение состояний визуально оформить, напр. "preloader icon", "purchase icon", "checked icon", и т.п.
     Дизайн/стиль продумать самостоятельно.

3. Сохранение состояния позиций
   После перезагрузки страницы, состояния позиций (в корзине он или нет) должно сохраняться.

4. Подробное описание похиции
   При клике на название/изображение товара должна открывается модальное окно с карточкой товара.
   В карточке должны быть:
   - краткое описание позиции
   - цена
   - слайдер, содержащий 2-4 изображения
     Дизайн модального окна продумать самостоятельно.

Код приложения должен быть размещен на gihub/gitlab/bitbucket.
Проект должен запускаться с помощью webpack-dev-server, а процесс билдинга и запуска проекта должен быть описан в README.
Или же можно выложить проект на хостинг, и прикрепить ссылку на работающее приложение в README.md или e-mail.

#### deploy: https://online-art-store-n1982.vercel.app/

