# Инструкция по работе с Git


## Что такое git?

## Подготовка репозитория

Для создания репозитория используется команда __*git init*__.
Находясь в нужной папке, используем команду __*git init*__ в **термианле**, и эта папка станет репозиторием

## Создание "сохранений"

### Добавление файла к коммиту

Для добавления файла к коммиту используется команда

__*add <Имя_файла>*__

### Создание коммита

Для создания нового "сохранения" используется команда 

__*git commit -m"<Информация о сохранении>"*__ 

В терминале, находясь в папке репозитория, вводится команда. Оставлять описание "сохранения" **ОБЯЗАТЕЛЬНО** !

## Журнал изменений

Для просмотра журнала изменений используется команда

__*git log*__

## Перемещение между коммитами

Для перемещения между сохранениями используется команда:

__*git checkout <номер_коммита>*__

**Номер_коммита** берется из _журнала изменений_.

При переходе на предыдущее сохранение из актуального состояния, мы попадаем в состояние **detached head**.
Для возвращение к актуальному состаянию, необходимо использовать команду:

__*git checkout master*__

## Ветки в git

Для отображения всех веток используется команда:

__*git branch*__

В отобразившемся списке будут перечислены все ветки. Активная ветка выделяется зеленым цветом и звездочкой перед названием. Пример:

      неактивная_ветка
    * активная ветка

### Создание ветки

Для создания новой ветки используется команда:

__*git branch*__ *имя_ветки*

Автоматического перехода на созданную ветку **не происходит**.

### Удаление ветки

Для удаление ветки используется команда:

__*git branch -d*__ *имя_ветки*

## Слияние веток и разрешение конфликтов

Для слияния веток используется команда:

__*git merge*__ *имя_ветки*

В случае, если конфликтов не возникнет, то все строки из указанной ветки добавятся в текущую (активную), файл сохранится с учетом внесенных изменений (сохранять изменения вручную не требуется), и будет сгенерирован автоматический коммит.

Если кофликт возникнет, то придется отредактировать получаемый результат самому, вручную сохранить его и создать новый коммит при помощи команд __*git add имя_файла*__ и __*git commit -m "комментарий_коммита"*__ .