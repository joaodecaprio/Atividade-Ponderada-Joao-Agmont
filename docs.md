### Documentação do protótipo
Este protótipo consiste em um semáforo offline, feito em um protoboard, que posseu 3 leds, dentre eles, um vermelho, um amarelo e um verde. Cada led possue um resistor pois o resistir serve para limitar a corrente elétrica que passa pelo LED, protegendo-o de queimar por sobrecarga. Um LED é um componente sensível e pode ser danificado por excesso de corrente, mesmo com uma pequena mudança na tensão. Os jumpers fêmea-macho foram usados para interligar o Arduino à protoboard. Os leds ascedem em intervalos de tempo diferente, no caso do led vermelho, o progrmama mantém a luz dele ascesa por 6 segundos, no caso do amarelo a duração é de 2 segundos e o led verde ascende por 4 segundos, isso é um ciclo contínuo e automatizado pelo programa utilizado a função tempoMillis() usa o millis(), que conta o tempo desde que o Arduino foi ligado, para controlar a duração de cada fase sem bloquear o loop principal diferente do delay.

### Imagens : 
<img src="assets/WhatsApp Image 2025-10-31 at 10.13.11.jpeg" alt="Imagem" width="350" >
<img src="assets/WhatsApp Image 2025-10-31 at 10.13.12 (1).jpeg" alt="Imagem" width="350">
<img src="assets/WhatsApp Image 2025-10-31 at 10.13.12.jpeg" alt="Imagem" width="350">

### Link : https://youtube.com/shorts/Ry3aNy9_Gbs?feature=share

### Arduino Code: 
```cpp

//Código dos leds
int ledVermelho = 8;
int ledAmarelo = 9;
int ledVerde = 10;
// Controle de tempo
unsigned long tempoAnterior = 0;
int estado = 0; // 0 = vermelho, 1 = verde, 2 = amarelo

void setup() {
  pinMode(ledVermelho, OUTPUT);
  pinMode(ledAmarelo, OUTPUT);
  pinMode(ledVerde, OUTPUT);
}

void loop() {
  unsigned long tempoAtual = millis();

  switch (estado) {
    case 0: // VERMELHO
      digitalWrite(ledVermelho, HIGH);
      digitalWrite(ledAmarelo, LOW);
      digitalWrite(ledVerde, LOW);
      if (tempoAtual - tempoAnterior >= 6000) { // 6 segundos
        estado = 1;
        tempoAnterior = tempoAtual;
      }
      break;

    case 1: // VERDE
      digitalWrite(ledVermelho, LOW);
      digitalWrite(ledAmarelo, LOW);
      digitalWrite(ledVerde, HIGH);
      if (tempoAtual - tempoAnterior >= 4000) { // 4 segundos
        estado = 2;
        tempoAnterior = tempoAtual;
      }
      break;

    case 2: // AMARELO
      digitalWrite(ledVermelho, LOW);
      digitalWrite(ledAmarelo, HIGH);
      digitalWrite(ledVerde, LOW);
      if (tempoAtual - tempoAnterior >= 2000) { // 2 segundos
        estado = 0;
        tempoAnterior = tempoAtual;
      }
      break;
  }
}
```
### Tabela de Avaliação entre Pares
#### Avaliador: Guilherme Schmidt
|Critério|  Contempla (Pontos)| Contempla Parcialmente (Pontos) |Não Contempla (Pontos) |Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores   |3  |   || |
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo |3  |   | | |
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |  3|   |   | |
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |   |  0,5 |   | |
| | | | |Pontuação Total: 9,5|

### Tabela de Avaliação entre Pares
#### Avaliador: Lucas Lopes
|Critério|  Contempla (Pontos)| Contempla Parcialmente (Pontos) |Não Contempla (Pontos) |Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores   |3  |   || |
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo |3  |   | | |
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |  3|   |   | |
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |   |  0,5 |   | |
| | | | |Pontuação Total: 9,5|

