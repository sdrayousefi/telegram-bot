import schedule
import time
from telegram import Bot

TOKEN = 8885330259:AAGZgU4oB0A4SfYgKuE5oEYvoVY9GkBjLdM

CHAT_ID = 6165008770

bot = Bot(token=TOKEN)

def morning():
    bot.send_message(
        chat_id=CHAT_ID,
        text="صبح بخیر عشقم ❤️ امیدوارم روز خوبی داشته باشی"
    )

def night():
    bot.send_message(
        chat_id=CHAT_ID,
        text="شب بخیر عزیزم، خواب‌های قشنگ ببینی ❤️"
    )

schedule.every().day.at("08:00").do(morning)
schedule.every().day.at("23:00").do(night)

while True:
    schedule.run_pending()
    time.sleep(30)
