---
title: "dataview- плагин obsidian"
Alias: 
tags:
- green/seed
date: 2023-08-04 10:59
---
Links:  
12.06.2022 / 1755  
[[notes/zero/00 Obsidian]]  
[link](https://www.youtube.com/watch?v=YMSQFv65D9g) - видео с настройкой и примерами- {Как вести список прочитанного в Obsidian.md}  
[link](https://github.com/blacksmithgu/obsidian-dataview)  - гитхаб dataview  
[link](https://blacksmithgu.github.io/obsidian-dataview/query/queries/)  - wiki  
—  
[[notes/zero/10 dataview- плагін obsidian приклади використання 01 dataview]]  
—  
==Для візуалізації== цього плагіна треба використовувати такий код:

>
> ```dataview 
> ```
>

### **Запит**
Після того як ви анотували документи тощо за допомогою метаданих, ви можете запросити їх, використовуючи будь-який із чотирьох режимів запиту.  
**Мова запитів Dataview (DQL)**  
**Inline Expressions**: DQL  
**DataviewJS**  
**Inline JS Expressions**

що б подивитися == приклад використання == перед посиланням надрукуй !

### Мова запитів підтримує такі типи уявлень, описані нижче:

1. **==TABLE==**: традиційний вид подання; один рядок на точку даних із кількома стовпцями польових даних.
1. ## Угруповання за статусами DataView (маленькі таблиці для прочитань: переглянуто, дивитися):

	```md 
	table 
	 rows.file.link as Films from "0 Creation/Фильмы" 
	group by status sort status
	```

	приклад використання  
	[[notes/zero/10 dataview- плагін obsidian приклади використання 01 dataview#Группировка по статусам DataView маленькие таблицы для прочтений просмотрено буду смотреть]]  
	2. ## Пример Большей таблицы DataView (с картинками)

	```md
	table 
	 recommendation,
	 rating,
	 genre,
	 ("![coverimg|200](" + cover + ")") as Cover
	from "0 Creation/Фильмы"
	sort rating desc
	
	```

	приклад використання  
	[[notes/zero/10 dataview- плагін obsidian приклади використання 01 dataview#Пример Большей таблицы DataView с картинками]]



2. **==LIST==** : список страниц, соответствующих запросу. Вы можете вывести одно связанное значение для каждой страницы.
	## смотреть тег

	```md
	list from #сделать
	```

	приклад використання  
	[[notes/zero/10 dataview- плагін obsidian приклади використання 01 dataview#смотреть тег]]

3. **==TASK==** : список задач, страницы которых соответствуют заданному запросу.
	## Список всех задач в незавершенных проектах:

	```md
	task from #projects/active
	```

	пример использования  
	[[notes/zero/10 dataview- плагін obsidian приклади використання 01 dataview#Список всех задач в незавершенных проектах]]
	


