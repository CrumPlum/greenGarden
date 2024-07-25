---
title: "py wiki"
Alias: wiki
tags:
- green/seed
date: 2024-07-24 10:15
---
Links:  
[[notes/python - cmd, компеляція|py]]
—

## beautifulsoup4
bs4 - бібліотека для розпарювання сторінок

## requests
бібліотека для отримання запитів get/post (та інших)библиотека для получения get/post запросов (и других)

[c тайм](https://youtu.be/XwDlcW_WsmU?si=1G3y0YP7nQNhSzse&t=504)
```
params = {'q': 'python'}

response = requests.get('link', params=params)

response_json = response.json()

print(response_json['total_count'])
```
для тестов get/post можно використовувати сайт [https://httpbin.org/#/HTTP_Methods](https://httpbin.org/#/HTTP_Methods)

## import pprint
гарний вивід словників
data = response.json()
pprint.pprint(data)

