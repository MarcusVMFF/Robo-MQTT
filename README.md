#  🚗 **Controle Remoto de Carrinho MQTT com Pico W**



Projeto individual para demonstrar o controle remoto de um carrinho de dois motores utilizando a placa Raspberry Pi Pico W e a placa BitDogLab (ou componentes equivalentes). A comunicação é estabelecida via Wi-Fi, e os comandos são enviados e recebidos através do protocolo MQTT. Desenvolvido em linguagem C para a residência TIC 37 - Embarcatech


---



## 🔎 **Objetivos**

O objetivo principal é desenvolver um sistema embarcado capaz de:
* Conectar o Raspberry Pi Pico W a uma rede Wi-Fi.
* Estabelecer comunicação com um broker MQTT para receber comandos e enviar status.
* Controlar remotamente os movimentos de um carrinho (frente, trás, parar) com base nas mensagens MQTT recebidas.
* Fornecer feedback visual do estado do carrinho utilizando os LEDs RGB da placa BitDogLab.
* Implementar funcionalidades básicas de um cliente MQTT, como subscrição a tópicos.

---


## 📊 **Video do Projeto:** (https://drive.google.com/file/d/1FtotyjZEnWoRuMc5SaY-uPhUAqrMbfKW/view?usp=sharing)



## 🛠️ **Tecnologias Utilizadas**


- **Linguagem de Programação:** C / CMake

- **Placas Microcontroladoras:**

  - BitDogLab

  - Pico W
  
- **Protocolos:**
  - Wi-Fi
  - MQTT

---



## 📖 **Como Utilizar**

1.  **Configuração:**
    * No arquivo `.c` principal, configure as seguintes macros com suas credenciais e informações do broker:
        ```c
        #define WIFI_SSID "NOME_DA_SUA_REDE_WIFI"
        #define WIFI_PASSWORD "SENHA_DA_SUA_REDE_WIFI"
        #define MQTT_SERVER "IP_OU_HOSTNAME_DO_SEU_BROKER_MQTT"
        #define MQTT_USERNAME "SEU_USUARIO_MQTT" // Se necessário
        #define MQTT_PASSWORD "SUA_SENHA_MQTT"   // Se necessário
        ```
2.  **Operação:**
    * Após o Pico conectar-se ao Wi-Fi e ao broker MQTT, envie comandos para os seguintes tópicos MQTT (usando um cliente MQTT como MQTT Explorer, IoT MQTT Panel, etc.):
        * **`/led`**:
            * `On` ou `1`: Aciona a ré e liga o LED vermelho.
            * `Off` ou `0`: Para o motor (se em ré) e desliga o LED vermelho.
        * **`/frente`**:
            * `On` ou `1`: Aciona movimento para frente e liga o LED verde.
            * `Off` ou `0`: Para o motor (se em frente) e desliga o LED verde.
        * **`/print`**: Envia uma mensagem para ser impressa no console serial do Pico.
    * Pressione o `botaoB` (GPIO 6) a qualquer momento para colocar o Pico em modo `reset_usb_boot`.

---


## 📊 **Funcionalidades Demonstradas**

- **Controle de Motores DC:** Acionamento direto dos pinos de controle de dois motores para movimento.
- **Comunicação Wi-Fi:** Utilização do módulo CYW43 do Pico W para conexão à rede.
- **Cliente MQTT:**
    - Conexão a um broker MQTT.
    - Subscrição a múltiplos tópicos.
    - Publicação de mensagens em tópicos.
    - Implementação de "Last Will and Testament" para status online.
    - Geração de um Client ID único baseado no ID da placa.
- **Manipulação de GPIOs:**
    - Controle de LEDs RGB para feedback visual.
    - Leitura de botão físico.
- **Interrupções:** Uso de interrupção de GPIO para o botão de reset para o modo bootloader.
