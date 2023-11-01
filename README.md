Задание 5.

Выполнить верстку формы обратной связи

Ссылка на макет
Срок выполнения: 2 недели

Реализовать валидацию полей формы с помощью JavaScript по следующим правилам:

Все текстовые поля формы являются обязательными для заполнения
Поле "E-mail" должно содержать валидный адрес электронной почты. Для проверки валидности email использовать регулярное выражение:
/^([a-zA-Z\-0-9_]+|([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)+)|(".+"))@(([a-zA-Z\-0-9]+\.)+[a-zA-Z\-0-9]{2,})$/
Поле "E-mail" не должно содержать более 255 символов
Поле "Ваше сообщение" не должно содержать более 1000 символов
Чекбокс с подтверждением обработки персональных данных обязателен к принятию
Допустимые форматы прикрепляемых файлов: .pdf, .doc, .docx
Логика валидации:

Проверка на валидность текстового поля происходит при потере этим элементом фокуса
Если проверка на валидность не успешна, то под соответствующим полем выводится сообщение с описанием ошибки
Если текстовое поле содержало ошибку, то сообщение об ошибке очищается после начала ввода
Если хотя бы одно поле формы содержит ошибку валидации, то отправка формы невозможна и кнопка "Отправить" выключена
Отправка данных формы должна выполняться с помощью fetch API по адресу /form
Форма должна отправляться без перезагрузки страницы

Дополнительно:

Расширить поведение input-file, добавив возможность прикреплять несколько файлов
Также добавить валидацию для прикрепляемых файлов:

Размер каждого файла не должен превышать 5Mb
Ограничить количество прикрепляемых файлов. Максимум 2 файла
Работа с компонентами
Создание компонента
Для генерации pug, scss, js файлов компонента необходимо ввести команду:

npm run component:create [название-компонента]
[название-компонента] - произвольное название компонента, записанное латиницей

Например:

npm run component:create example-button
Таким образом в папке src/components будет создана папка example-button с готовыми для работы pug, scss, js файлами внутри.
Все созданные файлы будут добавлены в сборщик автоматически

Для инициализации js-скриптов компонентов необходимо вручную добавить импорт в файл /src/app/js/common.js и добавить созданный компонент в объект allComponents

Удаление компонента
Для удаления существующего компонента необходимо ввести команду:

npm run component:remove [название-компонента]
[название-компонента] - произвольное название компонента, записанное латиницей

Например:

npm run component:remove example-button
Таким образом в папке src/components будет удалена папка example-button
Все pug, scss файлы, относящиеся к компоненту будут удалены из сборщика автоматически

Работа с проектом
Требования к системе
Node.js (v.16+)
npm (v.7+)
Запуск проекта
Установить зависимости
npm i
Запустить локальную dev-сборку
npm run dev
Запущенный локальный сервер будет доступен в браузере по адресу localhost:3000
Краткое описание файловой структуры
/
├── build_modules
└── src
    ├── app
    │   ├── js
    │   │   └── base
    │   └── common.js
    ├── assets
    │   ├── fonts
    │   ├── icons
    │   ├── images
    │   └── videos
    ├── components
    └── pages
build_modules - служебная директория, необходимая для сборки и запуска проекта. В рамках задания изменять содержимое папки нельзя
src - основная рабочая директория, содержащая исходный код проекта
src/app - директория, содержащая основные файлы приложения
src/app/js - директория, содержащая основную логику приложения
src/app/common.js - основной js-файл, точка входа для всех скриптов приложения
src/app/base - директория для хранения базовых js-классов
src/assets - необязательная директория для хранения статичных ресурсов (шрифты, изображения, видео, иконки)
src/components - директория для хранения исходного кода компонентов. Каждый компонент располагается в отдельной папке и может состоять из pug, scss и ts файлов
src/pages - директория для хранения статичных страниц
