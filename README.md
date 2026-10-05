# Automation-Testing
## Flipkart
### Code
```
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()

driver.get("https://www.flipkart.com/")

time.sleep(3)

# Click Login
login = driver.find_element(
    By.CSS_SELECTOR,
    "a[title='Login']"
)

driver.execute_script("arguments[0].click();", login)

time.sleep(3)

# Enter mobile number
mobile = driver.find_element(
    By.CSS_SELECTOR,
    "input[type='number']"
)

mobile.send_keys("7339413624")

print("Mobile number entered")

time.sleep(1)

# Click Continue
continue_button = driver.find_element(
    By.XPATH,
    "//button[contains(., 'Continue')]"
)

continue_button.click()

print("Continue clicked")

time.sleep(5)
input("Press Enter to close the browser...")
```
### Output
<img width="1245" height="967" alt="image" src="https://github.com/user-attachments/assets/d06c213d-cac2-4dd5-8189-6442a916ccf1" />

<img width="1253" height="957" alt="image" src="https://github.com/user-attachments/assets/4fa047dd-253d-42a6-82d0-54e5ea57b56c" />

<img width="1252" height="922" alt="image" src="https://github.com/user-attachments/assets/50c72f16-a679-4f82-a102-d77efc36e163" />


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

