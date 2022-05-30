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
* El pin debe estar conectado a algo que le suminestre alguna señal o fuente de lo contrario mostrara valores aleatorios.

### Al momento de usar WiFi.begin() todos los puertos adc2 quedaran inhabilitados
```c++
#include "WiFi.h"

int pin = 4;

void setup()
{
  Serial.begin(9600);
  WiFi.begin("ssid", "password");
}

void loop()
{
  int pot = analogRead(pin);
  Serial.println(pot);
  delay(100);
}

```
* Por lo tanto los puertos de adc2 no funcionaran como entradas cuando se use wifi pero si funcionaran los puertos adc1
