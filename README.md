# Моделирование потока сообщений Домена

Проектирование слабосвязанных систем требует большего, чем просто тщательно продуманные границы. Не менее важно тщательно определенное взаимодействие между ограниченными контекстами.

A [ограниченный контекст](https://martinfowler.com/bliki/BoundedContext.html ) - это подсистема в архитектуре программного обеспечения, согласованная с частью домена. Он может быть реализован в виде микросервиса или модуля внутри монолита.

Схема потока сообщений домена - это простая визуализация, показывающая поток сообщений (команд, событий, запросов) между участниками, ограниченными контекстами и системами для одного сценария.

## Форматы

Существует 2 основных формата, но формальной спецификации нет, поэтому настройте инструмент в соответствии с вашими потребностями, если базовые форматы вам не подходят.

### Отдельное сообщение и содержание

Формат отдельного сообщения и содержимого использует 2 формы для каждого сообщения: 1 для имени и порядка сообщения и отдельное поле для отображения содержимого сообщения (информации, которую оно содержит).

Преимущество этого формата заключается в том, что вы можете сосредоточиться на потоке сообщений, не увязая в содержимом сообщения с самого начала.

Начните с отображения только сообщений, передаваемых между отправителями и получателями (с номером заказа в сообщении).

![Поток сообщений - Просто Сообщения](resources/just-messages-no-contents.jpg )

Затем покажите содержимое каждого сообщения в отдельном поле рядом с каждым сообщением:

![Поток сообщений Сообщения и содержимое](resources/messages-and-contents.jpg )

### Комбинированное сообщение и содержание

Объединенный формат сообщения и содержимого использует единую форму для записи имени, порядка и содержимого сообщения.

![Пример потока сообщений](resources/domain-message-flow.jpg "Пример потока сообщений Домена")

Этот формат хорош, когда вы хотите сосредоточиться на содержании каждого сообщения с самого начала.

### Загрузки

- [Моделирование потока сообщений домена (резервное копирование платы miro)] (ресурсы/Моделирование потока сообщений домена-en-v1.rtb)

## Как использовать

Когда у вас есть начальный срез вашей архитектуры - вы определили возможные ограниченные контексты - вы можете приступить к проектированию потоков сообщений.

Начните с создания списка сценариев для моделирования. А затем для каждого сценария создайте диаграмму

При создании диаграммы типичным потоком является:

1. Начните с субъекта/контекста/системы
2. Создайте сообщение, которое они хотят отправить
3. Добавьте получателя сообщения и линию, соединяющую отправителя и получателя
4. Поместите сообщение рядом со строкой
5. Повторяйте шаги 1-4, пока ваш сценарий не будет завершен

Сообщение должно содержать 3 элемента:

1. Название сообщения
2. Важные данные, содержащиеся в сообщении
3. Порядок, в котором сообщение появляется в моделируемом потоке

## Советы по визуализации

Проблема номер один с диаграммами потока сообщений домена и диаграммами в целом - это слишком много информации. [Закон Миллера](https://en.wikipedia.org/wiki/Miller%27s_law ) является хорошей эвристикой для использования здесь. Стремитесь, чтобы на вашей диаграмме было от 5 до 9 сообщений.

Если вы обнаружите, что добавление данных в каждое сообщение нарушает ход выполнения, вы можете отложить раздел данных каждого сообщения до тех пор, пока не разместите все свои сообщения.

## Дополнительные ресурсы

- [Шаблон DDD: Библиотечные контексты](https://medium.com/nick-tune-tech-strategy-blog/ddd-pattern-library-contexts-d6ae81f462ef )
- [Контексты и суперконтексты картографа: Разделение границ, специфичных для домена, и границ, характерных для домена Contexts](https://medium.com/nick-tune-tech-strategy-blog/mapper-contexts-supercontexts-decoupling-domain-specific-and-domain-generic-bounded-contexts-5eb6a1e7c5fc)
- [Контексты обмена шлюзами](https://medium.com/nick-tune-tech-strategy-blog/gateway-interchange-contexts-899696e67848 )

## Участники

Спасибо всем [существующим и будущим участникам](https://github.com/ddd-crew/domain-message-flow-modelling/graphs/contributors ) и следующим лицам, которые внесли свой вклад в моделирование потока сообщений домена:

- [Каспер Гуния](https://github.com/cakper )
- [Зофия Херенди](https://twitter.com/zherendi )
- [Мелодия Ника](https://github.com/ntcoding )

Диаграммы потоков сообщений домена в значительной степени вдохновлены:

- [Диаграммы контейнеров C4 Саймона Брауна](https://c4model.com /)
- [Повествование о домене](https://domainstorytelling.org /)

## Вклады и отзывы

Нотация моделирования потока сообщений домена доступна для вас в свободном доступе. Кроме того, ваши отзывы и идеи приветствуются для улучшения техники или создания альтернативных версий.

Не стесняйтесь также отправлять нам запрос на извлечение с вашими примерами.

[![CC НА 4.0][cc-by-щит]][cc-by]

Эта работа лицензирована в соответствии с [Creative Commons Attribution 4.0 International
Лицензия][cc-by].

[![CC НА 4.0][cc-по-изображению]][cc-по]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-по-изображению]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-щит]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
