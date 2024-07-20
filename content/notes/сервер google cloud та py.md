---
title: "сервер google cloud та py"
Alias: google, sshm linux
tags:
- green/seed
date: 2024-07-16 02:06
---
Links:  
[как настроить FILEZILLA](https://www.youtube.com/watch?v=gJNAkjXNFTI )  
[как заходить, сохранять, private key, PuTTY](https://www.youtube.com/watch?v=BYKqASV_IkU)  
[Установка Telegram бота на ХОСТИНГ (СЕРВЕР) | Настройка сервера](https://youtu.be/X7_nqy57500?si=l6s131oeW-pGuu5H&t=604) c таймінгом  
—  
<--- [[notes/python - cmd, компеляція|python - cmd, компеляція]]

sudo adduser buonto  


как настроить FILEZILLA  [link](https://www.youtube.com/watch?v=gJNAkjXNFTI )  


как заходить, сохранять, private key, PuTTY  [link](https://www.youtube.com/watch?v=BYKqASV_IkU  )  

- явки
	buonto  
	buonto1Q
	
	buonto  
	1
	
	oleksandrkostyriev  
	12
	
	BOT-app  
	12  

Установка Telegram бота на ХОСТИНГ (СЕРВЕР) | Настройка сервера  
https://youtu.be/X7_nqy57500?si=l6s131oeW-pGuu5H&t=604

```
sudo apt -y install build-essential libssl-dev libffi-dev python3-dev
```

```
sudo apt install -y python3-venv
```

```
cd bot
```

```
ls
```
создать вірт середовище
```
python3 -m venv venv
```

```
source venv/bin/activate
```
//смотрим библиотеки и номера (через venv- script/activate) 
```
pip freeze
```
для WIN
```
python -m pip freeze
```
//запаковываем сюда 
```
requirements.txt 
```

---
УСТАНОВИТЬ СКРИН (от админа)
```
sudo apt -y install screen
```

```
pip3 install -r requirements.txt
```

```
source venv/bin/activate
```

```
cd bot
```

```
ls
```

```
screen -S bot
```

```
screen -ls
```

```
python3 app.py
```
удалить все сессии (возможно без screen -ls)
```  
screen -ls | grep -o '[0-9]*\.' | xargs -I {} screen -S {} -X quit
```

---
## відос з налаштуванням linux
```
Команды для сервера:
sudo apt update     Обновляем пакеты на сервере
sudo apt -y upgrade     Обновляем пакеты на сервере

dpkg-reconfigure locales     Устанавливаем нужные нам языки
LANG=en_US.UTF-8     Выбираем язык с нужной кодировкой 

sudo apt -y install python3-pip     Устанавливаем pip3
sudo apt -y install build-essential libssl-dev libffi-dev python3-dev     Устанавливаем несколько дополнительных пакетов и средств разработки 

sudo apt install -y python3-venv     Устанавливаем виртуальное окружение(VENV)

sudo apt -y install postgresql postgresql-contrib     Устанавливаем postgresql и дополнительный пакет -contrib, который содержит дополнительные утилиты и функциональные возможности

sudo -i -u postgres     Заходим из под пользователя postgres
createuser --interactive     Создаем новую роль
sudo adduser gino     Добавляем нововго пользователя
createdb gino     Создаем базу данных gino
alter role gino login password 'Vlad1234';     Изменяем пароль для пользователя gino

sudo apt -y install screen     Устанавливаем screen(нужен для запуска отдельного окна в фоне)

Команды для скрина:
screen -S screen_name  -  Создаем новый скрин
screen -ls  -  Посмотреть список запущенных скринов
screen -r screen_name  -  Открыть уже запущенный скрин
Ctrl + A + D  -  Свернуть запущенный скрин
Ctrl + A и ввести команду :quit  - Выключить скрин
```

<--- [[notes/python - cmd, компеляція|python - cmd, компеляція]]