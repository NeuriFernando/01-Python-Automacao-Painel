# Automação de Processos de Monitoramenteo Operacional

## Importando biblioteca

```
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import pyautogui
import time
import time
```
### Passo 1 - abrir o programa SIM NEXT Intalbras
```
pyautogui.press("win")
time.sleep(3) 
pyautogui.write("intelbras")
time.sleep(3) 
pyautogui.press("enter")

#delay para aguardar a abertura do sistema
time.sleep(25)

#Abrir as câmeras e rodar o RONDA automatica
pyautogui.click(x=226, y=461)
time.sleep(3) 
pyautogui.click(x=448, y=1070)
pyautogui.click(x=547, y=1178)
time.sleep(3)
pyautogui.click(button='right', x=662, y=295)
time.sleep(3) 
pyautogui.click(x=881, y=1485)
```

### Passo 2 - Abrir navegador com o link do Sistema

```
navegador = webdriver.Chrome()
navegador.maximize_window()
navegador.implicitly_wait(30)
navegador.set_page_load_timeout(220)
navegador.get("Colar link")

# Passo 2.1: Inserir chave e senha para acessar a aplicação
navegador.find_element('xpath', '//*[@id="chave"]').send_keys("User")
navegador.find_element('xpath', '//*[@id="senha"]').send_keys("Senha")
navegador.find_element('xpath', '//*[@id="login"]').send_keys(Keys.ENTER)
time.sleep(5)

# Passo 2.2: Abrir o painel dentro do Mdriver
navegador.find_elements('xpath','/html/body/nav/div[3]/div/div[3]/ul/li[5]/a')[0].click()
navegador.find_elements('xpath','//*[@id="05"]/li[1]/a/span')[0].click()

# Irá arrastar a tela do Mdrive para o location informado
pyautogui.click(x=232, y=35)
pyautogui.dragTo(13086, 2379, duration=5)
pyautogui.hotkey("win", "up")
pyautogui.press("F11")
navegador.find_elements('xpath','/html/body/main/div[1]/h1/div[2]/button[2]/i')[0].click()
```
