# Esp32-Entradas-Analogicas
Esto sucede porque los pines ADC2 no se pueden usar cuando se usa WiFi.
Por otro lado, los pines ADC1 se pueden usar incluso cuando WiFi está habilitado.

```c++
int pin = 15;

void setup()
{
  Serial.begin(9600);
}

void loop()
{
  int pot = analogRead(pin);
  Serial.println(pot);
  delay(100);
}
```
