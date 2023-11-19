# Projeto wpp automatizado

Este script apenas para fins de estudo de bibliotecas Python, utiliza a biblioteca `Selenium` para automação de envio de mensagens no WhatsApp Web. No entanto, é crucial respeitar as `políticas` de uso do `WhatsApp` para evitar violações que possam resultar em `banimento` da conta.

## Libs usadas no projeto

```python

from selenium import webdriver
from selenium.webdriver.common.keys import Keys

import pyautogui as tempo
import pyautogui as teclado

from selenium.webdriver.common.by import By

from openpyxl import load_workbook
import os
```
---

## Estrutura da base de contatos no whatsapp

| Nome         | Mensagem                   |
|--------------|----------------------------|
| contatoExemplo1     | corpo da mensagem contatoExemplo1 |
| contatoExemplo2     | corpo da mensagem contatoExemplo2 | 


## Demais destaques do Código

### Loop while
- Autenticação no WhatsApp Web

O script espera até que a página do WhatsApp Web seja carregada antes de prosseguir, é necessário iniciar a sessão manualmente antes de executar o script.

```python
while len(navegadorWeb.find_elements(By.ID, 'side')) < 1:
    # tempo de espera do logon da pag wpp web
    tempo.sleep(5)
```

### Loop de Envio de Mensagens
```python
for linha in range(2, len(celula_ativa['A']) + 1):
    contatoWpp = celula_ativa['A%s' % linha].value
    msgWpp = celula_ativa['B%s' % linha].value

    # localiza o path abaixo e busca pelo contato na variável "contatoWpp"
    navegadorWeb.find_element(By.XPATH, '//*[@id="side"]/div[1]/div/div[2]/div[2]/div/div[1]').send_keys(contatoWpp)
    tempo.sleep(1)

    # manipula a tecla enter do teclado
    teclado.press('enter')
    tempo.sleep(1)

    navegadorWeb.find_element(By.XPATH, '//*[@id="main"]/footer/div[1]/div/span[2]/div/div[2]/div[1]/div/div[1]').send_keys(msgWpp)

    tempo.sleep(1)
    teclado.press('enter')

```

### Uso da lib pyautogui para interação com teclado
```python

import pyautogui

```

## Execução do Script
Para executar o script, certifique-se de ter as bibliotecas necessárias instaladas. Você pode instalar as dependências usando:

```bash
pip install selenium openpyxl
pip install pyautogui
```

>Lembre-se de respeitar as políticas de uso do WhatsApp para evitar banimentos. O envio em massa de mensagens pode violar as `diretrizes` do WhatsApp, resultando em consequências para a conta. Reforçando que essa automação foi criada apenas com o intuito do meu aprendizado com libs `Python`.

---

[Confira o código no notebook do Jupyter]()


### Autor
---

<a href="https://medium.com/@freitas.atevilson/inova%C3%A7%C3%A3o-sim-todos-podemos-inovar-18934cfb787e">
 <img style="border-radius: 50%;" src="https://avatars.githubusercontent.com/u/62858618?s=400&u=5f6e68fa29a7808de7e4954f4017bae120585572&v=4" width="100px;" alt=""/>
 <br />
 <sub><b>Atevilson Freitas</b></sub></a> <a href="https://medium.com/@freitas.atevilson/inova%C3%A7%C3%A3o-sim-todos-podemos-inovar-18934cfb787e">🚀</a>


Automação de envio de mensagens no whatsapp

[![Linkedin Badge](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/atevilson-freitas/) 
[![Medium Badge](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@freitas.atevilson/inova%C3%A7%C3%A3o-sim-todos-podemos-inovar-18934cfb787e)