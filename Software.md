# Botão - LED com Raspberry Pi Zero W
## Configuração de acesso à rede e SSH
### 1. Acessar a unidade de disco boot(E:) (cartão MicroSD)
### 2. Criar um arquivo sem extensão nomeado ssh
### 3. Criar um arquivo nomeado wpa_supplicant.conf
Dentro do arquivo adicionar o seguinte texto:

> 1. network={
>  2.    ssid="NomeDaRede"
>  3.    psk="SenhaDaRede"}

Salvar o arquivo

## Configurando o LED e o Botão
### 1. Instalar a biblioteca [gpiozero](https://gpiozero.readthedocs.io/en/stable/development.html)
### 2. Código:
>1. from gpiozero import LED, Button
>2. from gpiozero import StatusBoard
>3. led = LED(7)
>4. button = Button(18)
>5. status = statusboard('wifi')
>6. status.wifi.led.off()
>7. status.wifi.button.when_pressed = status.wifi.led.on
