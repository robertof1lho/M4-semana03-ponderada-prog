### Vídeo
O vídeo mostrando a atividade está dentro da pasta assets.



### Avaliadora: Pietra Pasqualini Batista

| Critério                                                                                                 | Contempla (Pontos) | Contempla Parcialmente (Pontos) | Não Contempla (Pontos) | Observações do Avaliador |
|---------------------------------------------------------------------------------------------------------|--------------------|----------------------------------|--------------------------|---------------------------|
| Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores                | Até 3              | Até 1,5                            | 0                        |   3                        |
| Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo                  | Até 3              | Até 1,5                          | 0                        |  3                         |
| Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) | Até 3              | Até 1,5                          | 0                        |  3                         |
| Extra: Implmeentou um componente de liga/desliga no semáforo e/ou usou ponteiros no código | Até 1              |  Até 0,5                         | 0                        |  3                         |
|  |                                                             |  | |**Pontuação Total:** 10|


Relatório: A montagem do projeto foi feita utilizando Arduino Uno. Inicialmente, eu tentei utilizar o ESP32, mas não consegui usá-lo devido a erros na execução do código. Então, decidi seguir usando o Arduino, já que ele não apresentava esses problemas. Fui além nesta atividade aplicando um buzzer que toca de forma sincronizada com o LED vermelho quando ele é ativado.

código:
````
int RedledPin = 10;
int yellowledPin = 9;
int greenLedPin = 8;
int buzzerPin = 7; 

void setup() {
  pinMode(RedledPin, OUTPUT);
  pinMode(yellowledPin, OUTPUT);
  pinMode(greenLedPin, OUTPUT);
  pinMode(buzzerPin, OUTPUT);
}

void loop() {
  // Acende o LED vermelho e ativa o buzzer
  digitalWrite(RedledPin, HIGH);
  tone(buzzerPin, 1000);        // Toca o buzzer a 1000 Hz
  delay(4000);                  // Buzzer toca por 4 segundos
  noTone(buzzerPin);            // Desliga o buzzer após 4 segundos
  delay(4000);                  // LED vermelho permanece ligado por mais 4 segundos
  digitalWrite(RedledPin, LOW);

  // Acende o LED amarelo
  digitalWrite(yellowledPin, HIGH);
  delay(2000);                  // 2 segundos no amarelo
  digitalWrite(yellowledPin, LOW);

  // Acende o LED verde
  digitalWrite(greenLedPin, HIGH);
  delay(2000);                  // 2 segundos no verde
  delay(2000);                  // +2 segundos no verde (tempo adicional para pedestres)
  digitalWrite(greenLedPin, LOW);

  // Acende o LED amarelo novamente
  digitalWrite(yellowledPin, HIGH);
  delay(2000);                  // 2 segundos no amarelo
  digitalWrite(yellowledPin, LOW);
}

````