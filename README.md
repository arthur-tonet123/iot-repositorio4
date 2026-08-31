const int botao = 2; const int led1 = 8; const int led2 = 9;

int estado = 0; int leituraAtual; int leituraAnterior = LOW;

void setup() { pinMode(botao, INPUT); pinMode(led1, OUTPUT); pinMode(led2, OUTPUT);

digitalWrite(led1, LOW); digitalWrite(led2, LOW); }

void loop() { leituraAtual = digitalRead(botao);

// Detecta o momento em que o botão é apertado if (leituraAtual == HIGH && leituraAnterior == LOW) {

estado = (estado + 1) % 4;

if (estado == 1) {
  // 1º aperto
  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
}

else if (estado == 2) {
  // 2º aperto
  digitalWrite(led1, LOW);
  digitalWrite(led2, HIGH);
}

else if (estado == 3) {
  // 3º aperto
  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
}

else if (estado == 0) {
  // 4º aperto
  digitalWrite(led1, HIGH);
  digitalWrite(led2, LOW);
}

delay(200);
}

leituraAnterior = leituraAtual; }
