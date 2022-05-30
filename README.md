# Esp32 Entradas Analogicas
<img src="https://github.com/IDiegoUlises/Esp32-Entradas-Analogicas/blob/main/Images/Esp32-Entradas.jpg" width="800" height="500" />

* Los pines ADC2 no se pueden usar cuando se usa WiFi, los pines ADC1 se pueden usar incluso cuando WiFi esta habilitado.

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

# Conexion
<img src="https://github.com/IDiegoUlises/Esp32-Entradas-Analogicas/blob/main/Images/Conexion-Recortada.png" width="500" height="500" />


### Al momento de usar WiFi.begin() todos los puertos adc2 quedaran inhabilitados
```c++
#include "WiFi.h"

int pin = 15;

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
