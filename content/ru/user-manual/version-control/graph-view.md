---
title: Графический вид
layout: usermanual-page.hbs
position: 10
---

## Обзор

Граф версий контроля делает легким отслеживание прогресса и истории слияния веток проекта PlayCanvas.

В то время как панель контроля версий отображает простой список последних контрольных точек выбранной ветки, графический вид показывает гораздо больший (и расширяемый) вид всего графа контроля версий, включая контрольные точки, ветки и слияния:

![][overview-image]

## Запуск графического вида

Чтобы получить доступ к графическому виду, нажмите кнопку Граф в верхнем меню панели контроля версий (для текущей ветки редактора) или запись "Граф контроля версий" в выпадающем меню ветки.

![][access-buttons-image]

## Узлы графа

![][commit-node-image]

Узел графа будет содержать следующую информацию:

- Первые (до) две строки содержат (усеченное) описание контрольной точки.
- Следующая строка состоит из первых четырех символов GUID контрольной точки, его даты и имени пользователя, который его создал.
- Последняя строка содержит имя ветки.

## Контекстное меню узла графа

![][context-menu-image]

При нажатии на узел открывается контекстное меню с некоторыми или всеми следующими опциями, в зависимости от узла и прав доступа:

- **Просмотр изменений** - Запуск Diff View между этой контрольной точкой и ее непосредственным предшественником. ([Подробнее][view-changes])

- **Выбрать для сравнения** - Выберите первую контрольную точку из пары, которая будет сравниваться.

- **Сравнить с выбранным** - Запуск Diff View между текущим узлом и узлом, отмеченным через "Выбрать для сравнения".

![][compare-checkpoints-example]

- **Новая ветка** - Создать новую ветку из выбранной контрольной точки. ([Подробнее][new-branch])

- **Копировать данные** - Копирует полные (не усеченные) данные контрольной точки в формате JSON в буфер обмена, такие как GUID контрольной точки, идентификатор ветки, сообщение о контрольной точке и т. д.

- **Восстановить** (доступно только для текущей ветки редактора) - Восстановить состояние ветки до выбранной контрольной точки. ([Подробнее][restore-checkpoint])

- **Жесткий сброс** (доступно только для текущей ветки редактора) - Выполнить жесткий сброс до выбранной контрольной точки. ([Подробнее][hard-reset])

## Расширяемые узлы

![][node-expand-image]

Изначально графический вид отображает до 20 контрольных точек из каждой ветки и до 60 контрольных точек в общей сложности.

Треугольник в верхнем правом углу узла означает, что у него есть еще больше входящих или исходящих ребер (таких как ветки и слияния), и их можно расширить через контекстное меню "Расширить узел".

![][node-expand-example]

## Закрытые ветки

Граф также будет включать контрольные точки из закрытых веток, чтобы они всегда могли показывать оба родителя контрольной точки результата слияния. Они отмечены [x] после имени ветки:

![][closed-branches-image]

## Логика расположения узлов графа

Чтобы уменьшить размер графа как вертикально, так и горизонтально и облегчить навигацию, узлы графа располагаются определенным образом.

Ветка, которая была выбрана при нажатии кнопки Графический вид, показана слева. Все остальные ветки расположены справа от нее.

В общем случае каждая ветка занимает свою собственную колонку, но когда это возможно, граф размещает ветки одну над другой, чтобы предотвратить размещение узлов графа слишком далеко горизонтально.

Он также пытается расположить родительские контрольные точки ниже своих детей, когда это возможно.

В то же время он пытается избегать больших промежутков между узлами в ветке, изначально выбранной для графического вида, потому что скорее всего потребуется четкий обзор всех ее контрольных точек. Это и подобные соображения иногда могут привести к тому, что родительская контрольная точка будет показана выше своего ребенка в другой ветке и стрелка будет указывать вниз.

Цвет ребра помогает легко определить его направление, потому что он всегда соответствует цвету исходного узла.

Цвет каждой ветки остается неизменным при каждом открытии графического вида и не зависит от того, какая ветка была выбрана для его запуска.

Графический вид поддерживает масштабирование колесом прокрутки и панорамирование с помощью щелчка и перетаскивания.

[overview-image]: /images/user-manual/version-control/graph-view/overview.png
[closed-branches-image]: /images/user-manual/version-control/graph-view/closed-branches.png
[commit-node-image]: /images/user-manual/version-control/graph-view/commit-node.png
[node-expand-image]: /images/user-manual/version-control/graph-view/node-expand.png
[access-buttons-image]: /images/user-manual/version-control/graph-view/access-buttons.png
[node-expand-example]: /images/user-manual/version-control/graph-view/node-expand-example.gif
[compare-checkpoints-example]: /images/user-manual/version-control/graph-view/compare-checkpoints-example.gif
[context-menu-image]: /images/user-manual/version-control/graph-view/context-menu.png

[view-changes]: /user-manual/version-control/changes/
[new-branch]: /user-manual/version-control/branches/#creating-a-new-branch
[restore-checkpoint]: /user-manual/version-control/checkpoints/#restoring-a-checkpoint
[hard-reset]: /user-manual/version-control/checkpoints/#restoring-a-checkpoint