# Списки
Элементы списков могут быть двух размеров:

- Маленького (small) – height: 80px;
- Обычного (regular) – height: 120px

Внутренние отступы слева и справа – по 30px.

Содержимое элементов списка может иметь следующие виды:

- Объект (object)
- Объект с действием (object with action)
- Карточка (card)
- Карточка как действие (card as action)


## Объект

Элемент списка содержит лишь один кликабельный элемент – объект. У объекта практически всегда есть изображение и название. При наведении на них подсвечивается весь объект. Самый частый пример объекта – игрок. Объект является ссылкой, поэтому происходит переход на новую страницу (в случае с игроком – в его профиль).

Font-size названия объекта – 16px. Font-weight – bold.

----------------
List:

- List element
    - Actionable content
        - **.Object**
            - _.Image_
            - _.Title_
    - Other content

-----
```
.Object {
	.Image {
		border: 4px solid $white;
	};
	.Title {
		color: $text-color-primary;
	};
}

.Object:hover {
	.Image {
		@include shadow-brand-md;
		border: 4px solid $brand;
	};
	.Title {
		color: $text-color-brand;
	};
}
```

## Объект с действием
Помимо объекта в элементе списка имеется действие над этим объектом. В зависимости от контекста действие может быть кнопкой («добавить в друзья» – кнопка меняет вид, пользователь остается в списке), а может быть ссылкой («написать сообщение» – открывается чат).

---------------
List:

- List element
    - Actionable content
        - **Object**
            - _Image_
            - _Title_
        - **Action**
    - Other content

---------------
```
.Object {
	.Image {
		border: 4px solid $white;
	};
	.Title {
		color: $text-color-primary;
	};
}

.Object:hover {
	.Image {
		@include shadow-brand-md;
		border: 4px solid $brand;
	};
	.Title {
		color: $text-color-brand;
	};
}

.Action {
    width: 40px;
    height: 40px;
    @include shadow-dark-md;
}

.Action:hover {
    background-color: $brand;
    @include shadow-brand-md;
}
```


## Карточка
Карточка может содержать любой контент внутри себя. Карточка является ссылкой и кликабельна на всей площади карточки.

---------------
List:

- List element
    - **Card**
        - Content

----------------
```
.Card {
	background-color: $white;
}

.Card:hover {
	background-color: $grey-ultralight;
}
```

## Карточка как действие
Выглядит как объект с действием, однако при наведении ведет себя как карточка (меняет background всего элемента). Кликабельна вся площадь элемента. При клике, в отличие от карточки, вместо перехода по ссылке совершается действие на этой странице. Пример: добавление людей в групповой чат. 

---------------
List:

- List element
    - **Card**
        - Content
        - _Status_

------------------
```
.Card {
	background-color: $white;

	.Status {
        width: 40px;
        height: 40px;
		 background-color: $white;
		 @include shadow-dark-md;
}

.Card:hover {
	background-color: $grey-ultralight;
}

.Card .NewDefault {
	background-color: $white;

	.Status {
        width: 40px;
        height: 40px;
		 background-color: $brand;
		 @include shadow-dark-md;
	};
}

.Card:hover .NewDefault {
    background-color: $grey-ultralight;
}
```


Применение шаблонов на портале
=================

- **Рейтинг**: small - avatar
- **Друзья**: regular - avatar
- **Список чатов**: regular - card
- **Участники чата**: regular - avatar and action
- **Выбор собеседника (личный чат)**: regular - card
- **Выбор собеседника (групповой чат)**: regular - card as action
- **Обсуждения**: regular - card
- **Соседи**: regular - avatar and action
- **Поддержка**: regular - card
- **Уведомления**: regular - card

--------------

**Важно!**
Из всех списков убирается алфавитный указатель.

---------------

