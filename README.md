Projeto de Sistemas de Energia Renovável Offshore

Neste projeto, turbinas eólicas flutuantes e painéis solares flutuantes serão instalados para aproveitar o enorme potencial de geração de energia limpa que os oceanos oferecem. Usamos sensores de inclinação e velocidade do vento para monitorar a geração de energia e a integridade estrutural.

Os propósitos do projeto

Geração de Energia Limpa: Para produzir eletricidade sustentável, use painéis solares flutuantes e turbinas eólicas flutuantes.

Monitoramento de Integridade: A inclinação e a velocidade do vento são monitoradas por sensores para garantir a segurança e a eficiência das instalações.

Armazenamento de Energia: Para garantir um fornecimento constante de energia, implemente sistemas de armazenamento como baterias de alta capacidade e tecnologia de hidrogênio.

Transmissão de Energia: A energia produzida pode ser transferida para a rede elétrica onshore por meio de linhas de transmissão submarinas.

Componentes do Projeto

Arduino Uno
Potenciômetro (simulando o anemômetro)
Tilt Sensors (simulando o acelerômetro nos eixos X, Y e Z)
LED
Resistores
Protoboard
Fios 

Código do Arduino:

const int ventoSensorPin = A0; 
const int eixoSensorXPin = A1; 
const int eixoSensorYPin = A2; 
const int eixoSensorZPin = A3; 
const int statusLEDPin = 13; 

void setup() {
 
  Serial.begin(9600);
  
 
  pinMode(ventoSensorPin, INPUT);
  pinMode(eixoSensorXPin, INPUT);
  pinMode(eixoSensorYPin, INPUT);
  pinMode(eixoSensorZPin, INPUT);
  pinMode(statusLEDPin, OUTPUT);
}

void loop() {
 
  int velocidadeVento = analogRead(ventoSensorPin);
  int eixoX = analogRead(eixoSensorXPin);
  int eixoY = analogRead(eixoSensorYPin);
  int eixoZ = analogRead(eixoSensorZPin);
  
  
  Serial.print("Velocidade do Vento: ");
  Serial.println(velocidadeVento);
  Serial.print("Eixo X: ");
  Serial.println(eixoX);
  Serial.print("Eixo Y: ");
  Serial.println(eixoY);
  Serial.print("Eixo Z: ");
  Serial.println(eixoZ);
  
  
  if (eixoX > 600 || eixoY > 600 || eixoZ > 600) {
    digitalWrite(statusLEDPin, HIGH); // Acende o LED
  } else {
    digitalWrite(statusLEDPin, LOW); // Apaga o LED
  }
  
  
  delay(1000);
}

Link do tinkercad: https://www.tinkercad.com/things/0xT6f5w0247-gs-edge

Considerações finais
O objetivo deste projeto de energia renovável offshore é incentivar o uso de tecnologias limpas e inventivas para a geração de eletricidade, o que ajudará a preservar o meio ambiente e a promover o desenvolvimento sustentável das comunidades costeiras. A velocidade do vento e a inclinação das turbinas eólicas flutuantes são monitoradas continuamente para garantir a eficiência e a segurança do sistema.




