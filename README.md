## Nome e RM dos alunos

Miguel Marques RM: 555426
Pedro Ferronato RM: 554754

# Sistema de Monitoramento de Energia Renovável Offshore

## Objetivo

Desenvolver um sistema para monitorar a velocidade do vento e a inclinação de turbinas eólicas flutuantes utilizando sensores disponíveis no Tinkercad, com o objetivo de garantir a eficiência e a segurança das instalações de energia renovável offshore.

## Componentes Utilizados

- Arduino Uno
- 4 Potenciômetros
- LED
- Resistores
- Protoboard
- Fios de Conexão

## Descrição do Projeto

Este projeto combina a simulação de sensores de velocidade do vento e inclinação usando componentes disponíveis no Tinkercad para monitorar uma turbina eólica flutuante. O objetivo é garantir a eficiência operacional e a segurança estrutural da instalação.

### Simulação da Velocidade do Vento

Um potenciômetro é conectado ao pino analógico A0 do Arduino para simular um anemômetro, que mede a velocidade do vento. A leitura do valor analógico do potenciômetro representa a velocidade do vento.

### Simulação da Inclinação da Turbina

Três potenciômetros são conectados aos pinos analógicos A1, A2 e A3 do Arduino para simular os eixos X, Y e Z de um acelerômetro, que monitora a inclinação da turbina. Cada potenciômetro representa a inclinação em um eixo diferente.

### LED de Status

Um LED é conectado ao pino digital 13 do Arduino e serve como indicador visual de uma inclinação perigosa da turbina. Se qualquer valor dos eixos X, Y ou Z exceder um limiar definido, o LED acende para alertar sobre a condição.

## Instruções de Uso

### Configuração do Hardware

1. Conecte os quatro potenciômetros aos pinos analógicos A0, A1, A2 e A3 do Arduino.
2. Conecte um LED ao pino digital 13 do Arduino, com um resistor em série para limitar a corrente.
3. Monte todos os componentes na protoboard e faça as conexões necessárias usando fios de conexão.

### Configuração do Software

1. Baixe e instale a IDE do Arduino no seu computador.
2. Abra a IDE do Arduino e copie o código fornecido abaixo:

const int windSpeedPin = A0;
const int tiltXPin = A1;
const int tiltYPin = A2;
const int tiltZPin = A3;
const int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int windSpeed = analogRead(windSpeedPin);
  int tiltX = analogRead(tiltXPin);
  int tiltY = analogRead(tiltYPin);
  int tiltZ = analogRead(tiltZPin);

  Serial.print("Wind Speed: ");
  Serial.println(windSpeed);
  Serial.print("Tilt X: ");
  Serial.println(tiltX);
  Serial.print("Tilt Y: ");
  Serial.println(tiltY);
  Serial.print("Tilt Z: ");
  Serial.println(tiltZ);

  if (tiltX > 600 || tiltY > 600 || tiltZ > 600) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }

  delay(500);
}

3. Carregue o código no Arduino.

## Operação

1. Gire os potenciômetros para simular mudanças na velocidade do vento e na inclinação da turbina.

2. Observe os valores no monitor serial da IDE do Arduino.

3. Se a inclinação em qualquer eixo exceder o valor definido no código (600 neste exemplo), o LED acenderá para alertar sobre uma condição perigosa.

## Requisitos

1. IDE do Arduino

2. Placa Arduino Uno

3. Navegador Web (para acessar o Tinkercad)

## Informações Relevantes

1. Este projeto é uma simulação para demonstrar o uso de sensores no monitoramento de turbinas eólicas flutuantes. Para aplicações reais, sensores dedicados como anemômetros e acelerômetros devem ser usados, juntamente com sistemas de comunicação robustos para transmitir os dados monitorados a uma estação central.

