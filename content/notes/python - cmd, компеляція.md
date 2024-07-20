---
title: "python - cmd, компеляція"
Alias: py, exe, cmd, пу
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

Запустити програму:
```
python main.py
```

## <span style="color:rgb(57, 196, 239)">cmd як компелювати через cmd (прогу в exe)  (win)</span>
зайти в директорію  
~~~
cd C:\Users\Admin\Desktop\Python
  ~~~


треба встановити
```
pip install pyinstaller
```
py в exe
```
pyinstaller -F test.py
```

---
## <span style="color:rgb(57, 196, 239)">ізольоване середовище  </span>
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

установити пакети з файлу `requirements.txt`
```
pip install -r requirements.txt
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
## <span style="color:rgb(57, 196, 239)">os.system( 'pause' ) пауза елегантна у програмі  </span>
Закриття програми при натисканні клавіші консолі	
```
import os
os.system( 'pause' )
```

замість цього  
qwe= input('  ')

  
## інші посилання:
Учим Python за 1 час!  Профессионала (Хауди Хо)  
[link](https://www.youtube.com/watch?v=fp5-XQFr_nk)  
