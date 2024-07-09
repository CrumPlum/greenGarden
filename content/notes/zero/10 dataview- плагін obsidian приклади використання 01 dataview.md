12.06.2022 / 1810  
Tags: #inbox  
—  
Zero-Links & Links:  
[[notes/zero/00 Obsidian]]

— 
## смотреть тег

```dataview
list from #сделать 
```

## Группировка по статусам DataView (маленькие таблицы для прочтений: просмотрено, буду смотреть):

```dataview 
table rows.file.link as Films from "0 Creation/Фильмы" group by status sort status
```

## Пример Большей таблицы DataView (с картинками)

```dataview
table recommendation,rating,genre, ("![coverimg|200](" + cover + ")") as Cover
from "0 Creation/Фильмы"
sort rating desc

```

## ## Пример Большей таблицы DataView - буду смотреть

```dataview
table recommendation,rating,genre, ("![coverimg|200](" + cover + ")") as Cover
from "0 Creation/Фильмы"
where status = "буду смотреть"
sort rating desc

```

## Список всех задач в незавершенных проектах:

```dataview
task from #примерdataview
```

примерdataview
- [ ] 12
- [ ] 123