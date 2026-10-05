# Automation-Testing
## Flipkart
### Code
```
import undetected_chromedriver as uc
from selenium.webdriver.common.by import By
from selenium.webdriver.common.action_chains import ActionChains
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time, random

PHONE = "7339413624"

driver = uc.Chrome()
driver.maximize_window()
wait = WebDriverWait(driver, 20)
driver.get("https://www.flipkart.com")
time.sleep(3)
popup_xpath = "//*[contains(text(),'Log in for the best experience') or contains(text(),'Enter your phone number')]"
if not driver.find_elements(By.XPATH, popup_xpath):
    for xp in ["//a[normalize-space()='Login']", "//span[normalize-space()='Login']", "//*[normalize-space()='Login']"]:
        try:
            wait.until(EC.element_to_be_clickable((By.XPATH, xp))).click()
            break
        except Exception:
            continue

wait.until(EC.visibility_of_element_located((By.XPATH, popup_xpath)))
time.sleep(1)

box = wait.until(EC.element_to_be_clickable((
    By.XPATH,
    "//input[not(@name='q') and not(@type='hidden') and not(@type='checkbox') "
    "and not(contains(@class,'Pke_EE')) and not(@title)]"
    "[ancestor::*[.//text()[contains(.,'Log in for the best experience')]]]"
)))


driver.execute_script("arguments[0].focus(); arguments[0].click();", box)
time.sleep(0.5)

for ch in PHONE:
    box.send_keys(ch)
    time.sleep(random.uniform(0.1, 0.3))


print("Box value:", box.get_attribute("value"))

wait.until(EC.element_to_be_clickable((By.XPATH, "//button[normalize-space()='Continue']"))).click()

otp = input("OTP type pannunga: ").strip()
time.sleep(1)

actions = ActionChains(driver)
for ch in otp:
    actions.send_keys(ch).pause(random.uniform(0.1, 0.3))
actions.perform()

try:
    WebDriverWait(driver, 5).until(EC.element_to_be_clickable((
        By.XPATH, "//button[contains(.,'Verify') or contains(.,'Login')]"
    ))).click()
except Exception:
    pass

time.sleep(4)
print("Done:", driver.current_url)
input("Close panna Enter press pannunga...")
driver.quit()
```
### Output
<img width="1912" height="975" alt="Screenshot 2026-10-05 144935" src="https://github.com/user-attachments/assets/7c24fe14-aa3c-4150-8436-c2820bf7aaf3" />
<img width="1917" height="1076" alt="Screenshot 2026-10-05 144739" src="https://github.com/user-attachments/assets/e313acef-d171-4c8c-8dba-f838914980a5" />
<img width="1917" height="1078" alt="Screenshot 2026-10-05 145007" src="https://github.com/user-attachments/assets/83947a97-fae9-4f64-b68d-d8e3043e93b0" />





## Amazon
### Code
```
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()

driver.get("https://www.amazon.in/")

time.sleep(3)

login = driver.find_element(By.ID, "nav-link-accountList")
login.click()

time.sleep(3)

email = driver.find_element(By.ID, "ap_email_login")
email.send_keys("7339413624")
continue_button = driver.find_element(
    By.XPATH, "//input[@type='submit']"
)
continue_button.click()

time.sleep(3)

password = driver.find_element(By.ID, "ap_password")
password.send_keys("tb6@tb6@")

print("Password entered")

sign_in = driver.find_element(By.ID, "signInSubmit")
sign_in.click()

print("Sign-in clicked")

time.sleep(5)

print("Page title:", driver.title)

driver.quit()
```

### Output
<img width="1263" height="955" alt="image" src="https://github.com/user-attachments/assets/03c39d3c-89f4-41a0-ad03-a375c718fe4a" />

<img width="1282" height="971" alt="image" src="https://github.com/user-attachments/assets/c4a811bc-2f1e-483f-b0df-362a6e0ddeac" />

<img width="1278" height="913" alt="image" src="https://github.com/user-attachments/assets/974375b6-b679-4bdd-8b18-d19b537bdcbe" />

<img width="1913" height="1025" alt="image" src="https://github.com/user-attachments/assets/7f056f69-f032-4713-a2c4-d5447b53bc50" />

