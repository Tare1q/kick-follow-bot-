# kick-follow-bot-
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

# إعداد المتصفح
driver = webdriver.Chrome()  # تأكد من تحميل chromedriver ووضعه في نفس المجلد

# فتح موقع Kick
driver.get("https://kick.com/")

# تسجيل الدخول (استبدل القيم بمعلومات حسابك)
username = "YOUR_USERNAME"
password = "YOUR_PASSWORD"

# اضغط على زر تسجيل الدخول
login_button = driver.find_element(By.XPATH, '//button[contains(text(), "Log in")]')
login_button.click()
time.sleep(2)

# إدخال اسم المستخدم
username_input = driver.find_element(By.NAME, "username")
username_input.send_keys(username)

# إدخال كلمة المرور
password_input = driver.find_element(By.NAME, "password")
password_input.send_keys(password)
password_input.send_keys(Keys.RETURN)
time.sleep(3)

# الانتقال إلى قناة معينة ومتابعتها
channel_name = "TARE1Q"  # استبدلها باسم القناة المطلوبة
driver.get(f"https://kick.com/{channel_name}")
time.sleep(3)

# البحث عن زر المتابعة والضغط عليه
follow_button = driver.find_element(By.XPATH, '//button[contains(text(), "Follow")]')
follow_button.click()

print("تمت المتابعة بنجاح!")
time.sleep(5)
driver.quit()
