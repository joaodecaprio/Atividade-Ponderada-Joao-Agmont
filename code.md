'''cpp
// Pinos dos LEDs
int ledVermelho = 8;
int ledAmarelo  = 9;
int ledVerde    = 10;

// Controle de tempo
unsigned long tempoAnterior = 0;
int estado = 0;  // 0 = vermelho, 1 = verde, 2 = amarelo

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
      '''
  }
}
