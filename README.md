# Projeto SAÚDE
- Deivison Pertel – RM 550803
- Eduardo Akira Murata – RM 98713
- Link para o projeto -> https://wokwi.com/projects/382113881564584961
# Projeto Saúde - Monitoramento Remoto
## Descrição
Este projeto utiliza um microcontrolador ESP32 para monitorar a temperatura, umidade e presença em um ambiente. Os dados são enviados para um servidor MQTT, permitindo o acompanhamento remoto das condições do local.

## Componentes
- ESP32 DevKit v4: Microcontrolador Wi-Fi baseado no ESP32 para execução do código.
- DHT22: Sensor de temperatura e umidade para medição do ambiente.
- Sensor de Movimento PIR: Detecta a presença de movimento no ambiente.
- LED: Indica ocorrência de movimento ou alerta.

## Diagrama de Conexões

### Conexões Principais:
- DHT22: Conectado ao pino SDA (D2) do ESP32.
- PIR: Conectado ao pino GPIO4 (D4) do ESP32.
- LED: Conectado ao pino GPIO0 (D0) do ESP32.

## Configuração Wi-Fi e MQTT
- SSID e Senha Wi-Fi: Altere as variáveis ssid e password para as credenciais da sua rede Wi-Fi.
- Servidor MQTT: Configure o endereço do servidor MQTT nas variáveis mqtt_server e mqtt_port.
- Credenciais MQTT: Se necessário, configure um usuário e senha MQTT nas variáveis mqtt_user e mqtt_password.

## Funcionamento
O ESP32 lê os dados do sensor DHT22 e do sensor PIR. Os dados (temperatura, umidade e presença) são enviados para tópicos MQTT específicos. Caso o sensor PIR detecte movimento, um alerta é enviado para o tópico "projeto_saude/alerta" e o LED é aceso.

## Log de Publicação MQTT
O código inclui logs para acompanhar as publicações MQTT. Os logs incluem informações sobre o tópico e o payload enviado.

## Notas Importantes
Certifique-se de instalar as bibliotecas DHT e PubSubClient no Arduino IDE antes de carregar o código para o ESP32.
Para visualizar os logs e monitorar as publicações MQTT, utilize a janela Serial no Arduino IDE.
---
Este projeto é uma implementação simples para fins educacionais e pode ser expandido para atender a requisitos específicos. Fique à vontade para adaptar e melhorar conforme necessário.
