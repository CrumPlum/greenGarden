---
title: "electrobot - py"
Alias: py, bot, обленерго
tags:
- green/seed
date: 2024-07-05 17:56
---
Links:  
Безкоштовний хостинг [https://youtu.be/7mMrDIZWfcA?si=UdykvrunFKYzDpBF](https://youtu.be/7mMrDIZWfcA?si=UdykvrunFKYzDpBF)  
стаття хабр [link](https://habr.com/ru/articles/709314/)  
сайт с запуском бота [link](https://replit.com/)  
Робота по розкладу [https://youtu.be/OQLV7p_rd7o?si=qxuKtJdTzgVSGGfd](https://youtu.be/OQLV7p_rd7o?si=qxuKtJdTzgVSGGfd)  
—

```
import logging
from telegram import Update
from telegram.ext import Updater, CommandHandler, CallbackContext
import os
from config import TOKEN



import os
import requests
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.common.by import By
from webdriver_manager.chrome import ChromeDriverManager

# Настройка пути сохранения и имени файла
save_path = r"C:\Users\q2pj\OneDrive\Desktop"
file_name = "grafik0.png"
full_path = os.path.join(save_path, file_name)

# Настройка и запуск браузера
service = Service(ChromeDriverManager().install())
options = webdriver.ChromeOptions()
options.add_argument('--headless')  # Запуск без интерфейса браузера
browser = webdriver.Chrome(service=service, options=options)

# URL сайта с графиками отключений
url = "https://zakarpat.energy/customers/break-in-electricity-supply/schedule/"

try:
    # Переход на страницу
    browser.get(url)

    # Поиск изображения по тегу <img> (обновите селектор в зависимости от структуры сайта)
    img_element = browser.find_element(By.XPATH, "//img[contains(@src, '/upload/current-timetable/')]")

    # Получение ссылки на изображение
    img_url = img_element.get_attribute('src')

    # Скачивание изображения 
    response = requests.get(img_url)
    with open(full_path, 'wb') as file:
        file.write(response.content)

    print(f"Изображение успешно сохранено по пути: {full_path}")
finally:
    # Закрытие браузера
    browser.quit()
#------------------------------------------------------------------------------------------------------------
# Настройка логирования
logging.basicConfig(
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    level=logging.INFO
)
logger = logging.getLogger(__name__)

# Путь к файлу
file_path = r'C:\Users\q2pj\OneDrive\Desktop\grafik0.png'

def start(update: Update, context: CallbackContext) -> None:
    """Отправляет приветственное сообщение и ID пользователя при запуске команды /start."""
    user = update.effective_user
    welcome_message = f"Привет, {user.first_name}! Ваш ID: {user.id}"
    update.message.reply_text(welcome_message)

def send_file(update: Update, context: CallbackContext) -> None:
    """Отправляет файл при запуске команды /file."""
    if os.path.exists(file_path):
        update.message.reply_document(document=open(file_path, 'rb'))
    else:
        update.message.reply_text('Файл не найден.')

def main() -> None:
    """Запуск бота."""
    updater = Updater(TOKEN)
    dispatcher = updater.dispatcher

    # Добавление обработчиков команд
    dispatcher.add_handler(CommandHandler("start", start))
    dispatcher.add_handler(CommandHandler("file", send_file))

    # Запуск бота
    updater.start_polling()
    updater.idle()

if __name__ == '__main__':
    main()

```

качає с сайту обленерго скрін відключень і кидає на роб стіл

```
import os
import requests
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.common.by import By
from webdriver_manager.chrome import ChromeDriverManager

# Настройка пути сохранения и имени файла
save_path = r"C:\Users\q2pj\OneDrive\Desktop"
file_name = "grafik0.png"
full_path = os.path.join(save_path, file_name)

# Настройка и запуск браузера
service = Service(ChromeDriverManager().install())
options = webdriver.ChromeOptions()
options.add_argument('--headless')  # Запуск без интерфейса браузера
browser = webdriver.Chrome(service=service, options=options)

# URL сайта с графиками отключений
url = "https://zakarpat.energy/customers/break-in-electricity-supply/schedule/"

try:
    # Переход на страницу
    browser.get(url)

    # Поиск изображения по тегу <img> (обновите селектор в зависимости от структуры сайта)
    img_element = browser.find_element(By.XPATH, "//img[contains(@src, '/upload/current-timetable/')]")

    # Получение ссылки на изображение
    img_url = img_element.get_attribute('src')

    # Скачивание изображения 
    response = requests.get(img_url)
    with open(full_path, 'wb') as file:
        file.write(response.content)

    print(f"Изображение успешно сохранено по пути: {full_path}")
finally:
    # Закрытие браузера
    browser.quit()

```

відправляє файл зверху в лс по команді /file

```
import logging
from telegram import Update
from telegram.ext import Updater, CommandHandler, CallbackContext
import os
from config import TOKEN

# Настройка логирования
logging.basicConfig(
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    level=logging.INFO
)
logger = logging.getLogger(__name__)

# Путь к файлу
file_path = r'C:\Users\q2pj\OneDrive\Desktop\grafik0.png'

def start(update: Update, context: CallbackContext) -> None:
    """Отправляет приветственное сообщение и ID пользователя при запуске команды /start."""
    user = update.effective_user
    welcome_message = f"Привет, {user.first_name}! Ваш ID: {user.id}"
    update.message.reply_text(welcome_message)

def send_file(update: Update, context: CallbackContext) -> None:
    """Отправляет файл при запуске команды /file."""
    if os.path.exists(file_path):
        update.message.reply_document(document=open(file_path, 'rb'))
    else:
        update.message.reply_text('Файл не найден.')

def main() -> None:
    """Запуск бота."""
    updater = Updater(TOKEN)
    dispatcher = updater.dispatcher

    # Добавление обработчиков команд
    dispatcher.add_handler(CommandHandler("start", start))
    dispatcher.add_handler(CommandHandler("file", send_file))

    # Запуск бота
    updater.start_polling()
    updater.idle()

if __name__ == '__main__':
    main()


```