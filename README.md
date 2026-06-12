<div align="center">

# 🌱 GreenHealth IoT

<img src="https://img.shields.io/badge/status-em%20desenvolvimento-yellow" />
<img src="https://img.shields.io/badge/hardware-ESP32-blue" />
<img src="https://img.shields.io/badge/protocolo-MQTT-green" />
<img src="https://img.shields.io/badge/projeto-IoT-brightgreen" />
<img src="https://img.shields.io/badge/Arduino_IDE-00979D?logo=arduino&logoColor=white" />
<img src="https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white" />
<img src="https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black" />

<br><br>

<strong>🌿 Sistema IoT com ESP32, sensores e MQTT para monitoramento ambiental de plantas domésticas em tempo real.</strong>

</div>

---

## 🌿 Descrição do projeto

O **GreenHealth IoT** é uma versão reduzida do projeto **GreenHealth**, desenvolvida com foco em **Internet das Coisas** para o monitoramento de plantas domésticas.

O sistema utiliza um **ESP32** conectado a sensores para coletar dados relacionados ao ambiente e às plantas, como **umidade do solo**, **luminosidade**, **temperatura** e **umidade do ar**. Esses dados são enviados em tempo real para um broker MQTT e exibidos em uma interface web com gráficos e indicadores visuais.

A proposta do projeto é demonstrar como tecnologias de IoT podem auxiliar no cuidado de plantas, permitindo que o usuário acompanhe as condições do ambiente de forma mais precisa e prática.

---

## 🎯 Objetivo

Desenvolver um protótipo IoT capaz de monitorar variáveis ambientais relacionadas ao cuidado de plantas domésticas e disponibilizar essas informações em uma interface web em tempo real.

---

## 🧠 Funcionamento geral

O funcionamento do sistema ocorre da seguinte forma:

```txt
🌱 Sensores
   ↓
📟 ESP32
   ↓ MQTT
☁️ Broker EMQX
   ↓ WebSocket
💻 Dashboard Web
   ↓
👤 Usuário
```

O ESP32 realiza a leitura dos sensores, organiza os dados e envia as informações por MQTT. A interface web se conecta ao broker e atualiza os valores recebidos em tempo real.

---

## 🧰 Tecnologias utilizadas

<table>
  <tr>
    <th>🔌 Hardware</th>
    <th>💻 Software</th>
  </tr>
  <tr>
    <td>
      <ul>
        <li>ESP32</li>
        <li>Sensores de umidade do solo</li>
        <li>Sensores LDR para luminosidade</li>
        <li>Sensor DHT para temperatura e umidade do ar</li>
        <li>RTC DS3231</li>
        <li>Jumpers</li>
        <li>Protoboard</li>
        <li>Cabo USB ou fonte de alimentação</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>Arduino IDE</li>
        <li>HTML</li>
        <li>CSS</li>
        <li>JavaScript</li>
        <li>MQTT</li>
        <li>EMQX Broker</li>
        <li>PubSubClient</li>
        <li>WiFi</li>
        <li>Chart.js</li>
        <li>Eclipse Paho MQTT</li>
      </ul>
    </td>
  </tr>
</table>

---

## 📡 Comunicação MQTT

O projeto utiliza o protocolo **MQTT** para comunicação entre o ESP32 e a interface web.

<table>
  <tr>
    <th>Item</th>
    <th>Valor</th>
  </tr>
  <tr>
    <td>🌐 Broker utilizado</td>
    <td><code>broker.emqx.io</code></td>
  </tr>
  <tr>
    <td>🔌 Porta MQTT usada no ESP32</td>
    <td><code>1883</code></td>
  </tr>
  <tr>
    <td>🌍 Porta WebSocket para o dashboard</td>
    <td><code>8084</code></td>
  </tr>
</table>

---

## 📊 Dados monitorados

<table>
  <tr>
    <th>Sensor</th>
    <th>Informação monitorada</th>
    <th>Ícone</th>
  </tr>
  <tr>
    <td>Sensor de umidade do solo</td>
    <td>Umidade da planta</td>
    <td>💧</td>
  </tr>
  <tr>
    <td>LDR</td>
    <td>Luminosidade do ambiente</td>
    <td>☀️</td>
  </tr>
  <tr>
    <td>DHT</td>
    <td>Temperatura do ar</td>
    <td>🌡️</td>
  </tr>
  <tr>
    <td>DHT</td>
    <td>Umidade do ar</td>
    <td>🌫️</td>
  </tr>
  <tr>
    <td>RTC/API</td>
    <td>Data e hora da leitura</td>
    <td>🕒</td>
  </tr>
  <tr>
    <td>MQTT</td>
    <td>Status de conexão</td>
    <td>📡</td>
  </tr>
</table>

---

## 🔌 Esquema de ligação

### 📍 Tabela de conexões

<table>
  <tr>
    <th>Componente</th>
    <th>Pino no ESP32</th>
    <th>Observação</th>
  </tr>
  <tr>
    <td>Sensor de umidade do solo 1</td>
    <td>GPIO 26</td>
    <td>Entrada analógica</td>
  </tr>
  <tr>
    <td>Sensor de umidade do solo 2</td>
    <td>GPIO 33</td>
    <td>Entrada analógica</td>
  </tr>
  <tr>
    <td>Sensor de umidade do solo 3</td>
    <td>GPIO 35</td>
    <td>Entrada analógica</td>
  </tr>
  <tr>
    <td>LDR 1</td>
    <td>GPIO 25</td>
    <td>Entrada analógica</td>
  </tr>
  <tr>
    <td>LDR 2</td>
    <td>GPIO 32</td>
    <td>Entrada analógica</td>
  </tr>
  <tr>
    <td>LDR 3</td>
    <td>GPIO 34</td>
    <td>Entrada analógica</td>
  </tr>
  <tr>
    <td>DHT</td>
    <td>GPIO 27</td>
    <td>Entrada digital</td>
  </tr>
  <tr>
    <td>RTC SDA</td>
    <td>GPIO 12</td>
    <td>Comunicação I2C</td>
  </tr>
  <tr>
    <td>RTC SCL</td>
    <td>GPIO 13</td>
    <td>Comunicação I2C</td>
  </tr>
  <tr>
    <td>VCC dos sensores</td>
    <td>3V3 ou 5V</td>
    <td>Conforme o módulo utilizado</td>
  </tr>
  <tr>
    <td>GND dos sensores</td>
    <td>GND</td>
    <td>Terra comum</td>
  </tr>
</table>

> ⚠️ **Atenção:** os pinos **GPIO 34, 35, 36 e 39** do ESP32 são apenas entrada. Eles podem ser usados para sensores, mas não devem ser usados como saída.

---

## 🖼️ Foto ou diagrama do circuito

Adicione uma foto ou diagrama do circuito na pasta `assets/`.

### Exemplo de diagrama

```md
![Esquema de ligação](assets/esquema-ligacao.png)
```

### Exemplo de foto do protótipo

```md
![Protótipo GreenHealth IoT](assets/prototipo.jpg)
```

<div align="center">

<img src="assets/esquema-ligacao.png" alt="Esquema de ligação do GreenHealth IoT" width="700">

<br>

<em>Exemplo de espaço reservado para o esquema de ligação do circuito.</em>

</div>

---

## 🔗 Tópicos MQTT

Exemplo de tópicos utilizados:

```txt
greenhealth/temperatura
greenhealth/umidade_ar
greenhealth/data_hora
greenhealth/dados
```

Também é possível enviar todos os dados em um único tópico no formato JSON:

```json
{
  "temperatura": 28.5,
  "umidade_ar": 70,
  "solo1": 45,
  "solo2": 52,
  "solo3": 38,
  "luz1": 1800,
  "luz2": 2100,
  "luz3": 1650,
  "data_hora": "11/06/2026 18:30"
}
```

---

## 🖥️ Dashboard web

A interface web exibe os dados recebidos do ESP32 em tempo real.

### Recursos da interface

- 📊 Cards com valores atuais dos sensores
- 📈 Gráficos de linha em tempo real
- 📡 Status de conexão com o MQTT
- 💧 Visualização dos sensores de umidade
- ☀️ Visualização dos sensores de luminosidade
- 🌡️ Visualização da temperatura e umidade do ar
- 🔄 Atualização automática dos dados

<div align="center">

<img src="assets/dashboard.png" alt="Dashboard GreenHealth IoT" width="700">

<br>

<em>Espaço reservado para print do dashboard web funcionando.</em>

</div>

---

## 🚀 Instruções de uso

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/greenhealth-iot.git
```

### 2. Abrir o código do ESP32

Abra o arquivo na Arduino IDE:

```txt
codigo/greenhealth_iot.ino
```

### 3. Instalar as bibliotecas necessárias

Na Arduino IDE, instale as seguintes bibliotecas:

- WiFi
- PubSubClient
- DHT sensor library
- RTClib

### 4. Configurar Wi-Fi

No código do ESP32, altere os dados da rede Wi-Fi:

```cpp
const char* ssid = "NOME_DA_REDE";
const char* password = "SENHA_DA_REDE";
```

### 5. Configurar o broker MQTT

Verifique se o broker está configurado corretamente:

```cpp
const char* mqtt_server = "broker.emqx.io";
const int mqtt_port = 1883;
```

### 6. Conectar os sensores

Monte o circuito seguindo a tabela de conexões apresentada neste README.

### 7. Enviar o código para o ESP32

Na Arduino IDE:

1. Selecione a placa ESP32 correta.
2. Escolha a porta COM correspondente.
3. Clique em **Upload**.
4. Abra o **Monitor Serial** para verificar a conexão Wi-Fi e MQTT.

### 8. Abrir o dashboard

Abra o arquivo:

```txt
web/index.html
```

Ou publique a pasta `web/` em uma plataforma como:

- GitHub Pages
- Vercel
- Netlify

---

## 📌 Status do projeto

<table>
  <tr>
    <th>Módulo</th>
    <th>Status</th>
  </tr>
  <tr>
    <td>Leitura dos sensores</td>
    <td>✅ Implementado</td>
  </tr>
  <tr>
    <td>Envio MQTT</td>
    <td>✅ Implementado</td>
  </tr>
  <tr>
    <td>Dashboard web</td>
    <td>✅ Implementado</td>
  </tr>
  <tr>
    <td>Gráficos em tempo real</td>
    <td>✅ Implementado</td>
  </tr>
  <tr>
    <td>Exibição de status MQTT</td>
    <td>✅ Implementado</td>
  </tr>
  <tr>
    <td>RTC para data e hora</td>
    <td>✅ Implementado</td>
  </tr>
  <tr>
    <td>Uso de API como alternativa ao RTC</td>
    <td>✅ Implementado</td>
  </tr>
  <tr>
    <td>Irrigação automática</td>
    <td>🔜 Futuro</td>
  </tr>
  <tr>
    <td>Inteligência artificial</td>
    <td>🔜 Futuro</td>
  </tr>
</table>

---

## 🧪 Versão reduzida para IoT

Esta versão representa uma adaptação simplificada do projeto GreenHealth original. Ela mantém o foco no monitoramento ambiental e na comunicação IoT, mas não inclui todos os recursos planejados para a versão completa.

### ✅ Recursos presentes

- Monitoramento de sensores
- Envio de dados por MQTT
- Dashboard em tempo real
- Exibição de gráficos
- Status de conexão
- Data e hora das leituras

### 🔮 Recursos futuros

- Irrigação automatizada
- Cadastro de plantas
- Perfis botânicos por espécie
- Alertas personalizados
- Histórico de leituras
- Integração com previsão do tempo
- Recomendações automáticas
- Uso de inteligência artificial

---

## 📚 Aprendizados

Durante o desenvolvimento do projeto foram trabalhados conceitos como:

- Leitura de sensores no ESP32
- Comunicação Wi-Fi
- Comunicação MQTT
- Integração entre hardware e web
- Uso de JSON
- Criação de dashboard
- Gráficos em tempo real
- Organização de projeto para GitHub

---

## 📦 Entrega do projeto

Para a entrega ficar completa, o repositório deve conter:

- ✅ Código final comentado
- ✅ README.md completo
- ✅ Foto do protótipo
- ✅ Diagrama ou esquema de ligação
- ✅ Prints do dashboard funcionando
- ✅ Instruções de uso
- ✅ Lista de componentes
- ✅ Descrição dos tópicos MQTT

---

## 👨‍💻 Autor

Desenvolvido por **Samuel Chaves de Sá**.

Projeto acadêmico desenvolvido no curso de **Sistemas de Informação**, com foco em **IoT, automação, monitoramento ambiental e cuidado inteligente de plantas domésticas**.

---

## 📄 Licença

Este projeto é de uso acadêmico e experimental.

Sinta-se livre para estudar, adaptar e evoluir a ideia. 🌱
