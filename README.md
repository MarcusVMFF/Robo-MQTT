#  🚗 **Controle Remoto de Carrinho MQTT com Pico W**



Projeto individual para demonstrar o controle remoto de um carrinho de dois motores utilizando a placa Raspberry Pi Pico W e a placa BitDogLab (ou componentes equivalentes). A comunicação é estabelecida via Wi-Fi, e os comandos são enviados e recebidos através do protocolo MQTT. Desenvolvido em linguagem C para a residência TIC 37 - Embarcatech


---



## 🔎 **Objetivos**

O objetivo principal é desenvolver um sistema embarcado capaz de:
* Conectar o Raspberry Pi Pico W a uma rede Wi-Fi.
* Estabelecer comunicação com um broker MQTT para receber comandos e enviar status.
* Controlar remotamente os movimentos de um carrinho (frente, trás, parar) com base nas mensagens MQTT recebidas.
* Fornecer feedback visual do estado do carrinho utilizando os LEDs RGB da placa BitDogLab.
* Permitir o reset do microcontrolador para o modo bootloader através de um botão físico, facilitando a atualização do firmware.
* Implementar funcionalidades básicas de um cliente MQTT, como subscrição a tópicos, publicação de mensagens e o uso de "Last Will and Testament" para indicar o status online.

---



## 📊 **Video do Projeto:** https://drive.google.com/file/d/1G63GOcDMm1tIHZwsFUQiteUj-pUA8d1L/view?usp=drive_link



## 🛠️ **Tecnologias Utilizadas**



- **Linguagem de Programação:** C / CMake

- **Placas Microcontroladoras:**

  - BitDogLab

  - Pico W

- **Sistema Operacional:** Free-RTOS

---



## 📖 **Como Utilizar**



- Aperte o botão A para alterar entre o modo Diurno e Noturno



---



## 📊 **Funcionalidades Demonstradas**



- Controle de Concorrência pelas Threads(Tasks)

- Controle de Matriz de led 5x5

- Controle do Display SSD1306

- Controle de LED PWM

- Controle do buzzer

- Manipulação de botões e deboucing
