# 💡 Controle de LED por LDR com Arduino

## 📝 Descrição do Projeto

Este projeto utiliza um **Arduino Uno** para realizar a leitura da intensidade luminosa do ambiente por meio de um **sensor LDR (Light Dependent Resistor)**.

O LDR está conectado à entrada analógica **A0** do Arduino. A partir do valor lido, o programa verifica a quantidade de luz detectada e controla um LED conectado ao pino digital **13**.

O objetivo é demonstrar, de forma prática, como utilizar um **sensor analógico como entrada (INPUT)** e um **LED como saída (OUTPUT)** em um projeto com Arduino.

---

## 👥 Integrantes da Equipe

- **Leticia Halana** — Instrutora
- **Nome do integrante** — Fernando Alves de Lima

---

## 🛠️ Materiais e Componentes Eletrônicos

| Componente | Quantidade | Observação |
|---|---:|---|
| Arduino Uno | 1 un. | Microcontrolador utilizado no projeto |
| Sensor LDR | 1 un. | Responsável por detectar a luminosidade |
| LED | 1 un. | Indicador visual |
| Resistor | 2 un. | Utilizados no circuito |
| Protoboard | 1 un. | Montagem do circuito |
| Jumpers | Vários | Conexões entre os componentes |

---

## 🔌 Ligações do Circuito

As principais conexões utilizadas no projeto são:

| Componente | Arduino |
|---|---|
| LDR | A0 |
| LED | Pino 13 |
| GND | GND |
| Alimentação do circuito | 5V |

O LDR envia um valor analógico para o Arduino através do pino **A0**. O LED é controlado pelo pino digital **13**.

---

### 📷Circuito completo

![Imagem do Circuito Completo](

### 📷Montagem na protoboard


---

## 💻 Código do Projeto

O código utilizado foi desenvolvido em **Arduino/C++**.

```cpp
int led = 13;
int ldr = A0;
int valor_ldr;

void setup() {
  pinMode(led, OUTPUT);
  pinMode(ldr, INPUT);
  Serial.begin(9600);
}

void loop() {
  valor_ldr = analogRead(ldr);
  Serial.println(valor_ldr);

  if (valor_ldr > 1000) {
    digitalWrite(led, HIGH);
    delay(1000);
  } 
  else {
    digitalWrite(led, LOW);
    delay(1000);
  }
}
```

O código acima corresponde ao arquivo fornecido para o projeto. 

---

## ⚙️ Funcionamento do Código

### 1. Declaração das variáveis

```cpp
int led = 13;
int ldr = A0;
int valor_ldr;
```

- `led` representa o pino digital 13.
- `ldr` representa a entrada analógica A0.
- `valor_ldr` armazena o valor obtido pelo sensor.

### 2. Configuração dos pinos

No `setup()`, o LED é definido como **saída (`OUTPUT`)** e o LDR como **entrada (`INPUT`)**. A comunicação serial também é iniciada em **9600 baud**. fileciteturn1file0L14-L18

### 3. Leitura do LDR

No `loop()`, o Arduino utiliza:

```cpp
valor_ldr = analogRead(ldr);
```

para realizar a leitura do valor analógico do LDR. O valor também é enviado para o Monitor Serial com `Serial.println(valor_ldr)`. fileciteturn1file0L20-L22

### 4. Controle do LED

O programa verifica se o valor do LDR é maior que **1000**:

```cpp
if (valor_ldr > 1000)
```

Quando essa condição é verdadeira, o LED é ligado. Caso contrário, o LED é desligado. Em ambos os casos, existe um intervalo de **1 segundo** entre as ações. 
---

## 🔄 Fluxo de Funcionamento

```text
        ☀️ Luz no ambiente
              ↓
          [ Sensor LDR ]
              ↓
       Entrada analógica A0
              ↓
        [ Arduino Uno ]
              ↓
     Verifica valor do LDR
              ↓
       Valor > 1000?
          ↙          ↘
        SIM           NÃO
         ↓             ↓
      LED ON         LED OFF
```

---

## 🎯 Objetivo

O objetivo do projeto é compreender como o Arduino pode:

- receber informações de um **sensor LDR**;
- realizar uma **leitura analógica**;
- enviar os valores para o **Monitor Serial**;
- tomar uma decisão utilizando uma estrutura condicional `if/else`;
- controlar um LED por meio de uma saída digital.

---

## 📚 Tecnologias Utilizadas

- **Arduino Uno**
- **Arduino IDE**
- **C/C++ (Arduino)**
- **Sensor LDR**
- **LED**
- **Protoboard**
- **Resistores**
- **Jumpers**

---

## 📁 Arquivos do Projeto

- `README.md` — documentação do projeto.
- `circuito-completo.png` — imagem do circuito completo.
- `circuito-protoboard.png` — imagem da montagem na protoboard.
- `codigo_arduino52.ino` — código utilizado no Arduino.

---

## 👨‍💻 Projeto

**Controle de LED por LDR com Arduino**

> Projeto desenvolvido para demonstrar a leitura de luminosidade com LDR e o controle de um LED utilizando Arduino.
