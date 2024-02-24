// Definir los pines que se van a utilizar
const int pirPin = 2; // Pin del sensor PIR
const int ledPin = 13; // Pin del LED

void setup() {
  pinMode(ledPin, OUTPUT); // Configurar el pin del LED como salida
  pinMode(pirPin, INPUT);  // Configurar el pin del sensor PIR como entrada
  digitalWrite(ledPin, LOW); // Apagar el LED inicialmente
  Serial.begin(9600); // Iniciar la comunicación serial para depuración (opcional)
}

void loop(){
  int pirValue = digitalRead(pirPin); // Leer el valor del sensor PIR

  if (pirValue == HIGH) { // Si el sensor detecta movimiento
    digitalWrite(ledPin, HIGH); // Encender el LED
    Serial.println("Movimiento detectado"); // Mensaje de depuración (opcional)
    delay(5000); // Esperar 5 segundos antes de apagar el LED
  } else {
    digitalWrite(ledPin, LOW); // Apagar el LED si no se detecta movimiento
  }
}
