# INSTALAR SELENIUM : pip install selenium
# INSTALAR SELENIUM : pip install webdriver-manager

from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.chrome.service import Service
from webdriver_manager.chrome import ChromeDriverManager
import time

driver = webdriver.Chrome(service=Service(ChromeDriverManager().install())) #Criando a aba do Chrome
driver.get('https://accounts.google.com/signin')

#copiar Xpath da input da pagina (Xpath é como um id que dificilmente é alterado ao sbrir e fechar a pagina)

email = "matheusbpython@gmail.com"
senha = "teto.2007"

# Função para procurar um elemento na pagina / Recebe dois parametros NAME e VALOR
email_input = driver.find_element(By.ID,'identifierId')

email_input.send_keys(email)
email_input.send_keys(Keys.RETURN)
time.sleep(5)

password_input = driver.find_element(By.XPATH, '//*[@id="password"]/div[1]/div/div[1]/input')

password_input.send_keys(senha)
password_input.send_keys(Keys.RETURN)
time.sleep(5)

# recusar_input = driver.find_element(By.XPATH, '//*[@id="yDmH0d"]/div[1]/div[1]/div[2]/div/div/div[3]/div/div[2]/div/div/button/span')
# recusar_input.send_keys(Keys.RETURN)
# time.sleep(5)

driver.get('https://youtube.com/')
time.sleep(5)


nameVideo =  "Programador Reprogramado"

caixadepesquisa_input = driver.find_element(By.NAME, 'search_query')
caixadepesquisa_input.send_keys(nameVideo)
caixadepesquisa_input.send_keys(Keys.RETURN)
time.sleep(5)


