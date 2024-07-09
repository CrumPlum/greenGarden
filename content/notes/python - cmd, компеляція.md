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
Учим Python за 1 час!  Профессионала (Хауди Хо)  
[link](https://www.youtube.com/watch?v=fp5-XQFr_nk)  
—  

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

```
pyinstaller -F test.py
```

ізольоване середовище

```
python -m venv myenv
```

встановити політику виконання

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

==os.system( 'pause' ) пауза елегантная в программе==

25.04.2021 / 1923  

Tags:  пауза pause ос os  
— @@  
/#Закрытие программы при нажатии клавиши для консоли	

```ctrl+c


import os
os.system( 'pause' )

```

вместо  
qwe= input('  ')

и...  
from math import *  
импорт других библиотек  
—  
Zero-Links  
[00 Python](00%20Python.md)

12  
—  
Links  
https://t.me/memsdigital/52