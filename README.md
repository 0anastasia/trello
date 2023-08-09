[![Build status](https://ci.appveyor.com/api/projects/status/1rqrxrdwxgtby7ft?svg=true)](https://ci.appveyor.com/project/0anastasia/trello)
https://0anastasia.github.io/trello/

## Работа с файлами, DnD
yarn
Фактически у вас есть доска, состоящая из колонок, в каждой колонке может быть несколько карточек.

Для упрощения сделаем следующие допущения:
1. Кол-во колонок фиксировано и равно 3
1. Новые колонки добавлять нельзя, удалять имеющиеся тоже
3. Перемещать колонки тоже нельзя

Что же можно:
1. Добавлять карточки с помощью кнопки 'Add another card'.
2. Удалять карточки - при наведении на карточку появляется иконка крестик ("\E951"), которая и удаляет карточку (обратите внимание в оригинальном Trello такой операции нет, есть только архивация, но мы для упрощения её ввели):

 
4. Перемещать карточки как внутри колонки, так и между колонками:

##### Процесс перемещения

1. Внешний вид до переноса (карточка находится на своём месте)

2. Внешний вид в момент переноса (карточка удаляется из своего начального положения)

Обратите внимание на следующие нюансы:
1. Внешний вид курсора ('grabbing')
2. Курсор по отношению к карточке остаётся там, где изначально схватили - не привязывается ни к левому краю, ни к центру, а там, где схватили карточку, т.е. можно схватить за нижний левый угол.

3. При наведении на другие позиции под карточку выделяется место по высоте равное размеру самой карточке, при это будет карточка ставится "до" или "после" элемента определяется исключительно позицией курсора.

##### Дополнительно

Дополнительные требования:
1. Храните всё состояние в LocalStorage так, чтобы после обновления страницы внесённые изменения сохранялись
1. Постоение DOM-дерева производите на базе состояния, хранящегося в LocalStorage

##### Упрощения

В целях упрощения сделайте только:
1. Возможность хранить текст (картинки, списки, цветовое оформление элементов не нужно)
2. Перемещение самой карточки (поворот делать не нужно)
3. Можете также не обрабатывать ситуацию, связанную с выносом элемента за пределы доски
