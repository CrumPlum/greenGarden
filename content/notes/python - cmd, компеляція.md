---
title: "python - cmd, компеляція"
Alias: exe, cmd, py
tags:
- green/seed
date: 2023-08-04 10:59
---
Links:  
21.04.2021 / 2017  
[[notes/zero/00 Python]]  
—  
---> [[notes/сервер google cloud та py|сервер google cloud та py]]

---
==//cmd як компелювати через cmd (прогу в exe)==  
//зайти в директорію  
~~~
cd C:\Users\Admin\Desktop\Python
  ~~~
Запкустить програму:

```
python main.py
```

//компеляция файлов(в exe):  
надо установить 

```
pip install pyinstaller
```

в exe

```
pyinstaller -F test.py
```

---
ізольоване середовище  
(після обов'язково зайти - 'myenv/scripts/activate')

```
python -m venv myenv
```

встановити політику виконання (в power shel)

```
Set-ExecutionPolicy RemoteSigned
```

запустити віртуальне середовище

```
myenv\Scripts\activate
```

подивитися версії пакетов

```
pip freeze
```

перевстановити пакет менеджерів

```
pip install --force-reinstall -v "aiogram==2.20.0"
```

явки, команди  
---> [[notes/сервер google cloud та py|сервер google cloud та py]]

---

==os.system( 'pause' ) пауза елегантная в программе==  
Tags:  пауза pause ос os  
/#Закрытие программы при нажатии клавиши для консоли	

```
import os
os.system( 'pause' )
```

вместо  
qwe= input('  ')

  
## інші посилання:
Учим Python за 1 час!  Профессионала (Хауди Хо)  
[link](https://www.youtube.com/watch?v=fp5-XQFr_nk)  
