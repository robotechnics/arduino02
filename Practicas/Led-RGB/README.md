# Led RGB

![Animación](practica.gif)

En esta práctica vamos a visualizar los colores rojos, verde y azul alimentando para cada color una sola parte gracias al uso de pines PWM de la placa de Arduino.

1.	[Materiales](#materiales)
2.	[Esquema eléctrico](#esquema-eléctrico)
3.	[Programación en mBlock](#programación-en-mblock)
4.	[Programación en Arduino](#programación-en-arduino)



---


<br><br>


## Materiales

Para llevar a cabo la práctica, vamos a necesitar los siguientes materiales:
- 1 Placa de Arduino UNO
- 1 Protoboard
- 4 latiguillos
- 1 Diodo Led RGB (ánodo común)
- 3 Resistencia


<br><br>


## Esquema eléctrico

Teniendo en cuenta las características técnicas de los diodos led que utilizamos en esta práctica, calculamos la resistencia del circuito aplicando la Ley de Ohm.

| Diodo Led RGB (ánodo común)      |        |
| -------------------------------- | ------ |
| Polarizado                       | Sí     |
| Diámetro                         | 5mm    |
| Itensidad de Corriente           | 20mA   |
| Tensión en Led (rojo)            | 2,1V   |
| Tensión en Led (verde)           | 3,3V   |
| Tensión en Led (azul)            | 3,3V   |

```
LED ROJO

V = 2,9V
I = 20mA

V = I x R ; R = V / I

R = 2,9V / 0,02A = 145Ω 

--

LED VDERDE Y AZUL

V = 1,7V
I = 20mA

V = I x R ; R = V / I

R = 1,7V / 0,02A = 85Ω 
```

Se conectan los componentes sobre la placa de prototipado.

![Esquema eléctrico](fritzing.png)


<br><br>


## Programación en mBlock

La programación de esta práctica consiste en encender los diferentes colores del led RGB.

![Programación en mBlock](mBlock.png)


<br><br>


## Programación en Arduino

Al igual que en el apartado anterior, programamos en Arduino IDE la práctica propuesta.

```
/**
 * Led RGB
 * 
 * Un led RGB permite visualizar una luz de diferentes colores en 
 * función de la alimentación de cada una de sus patillas. En esta 
 * práctica vamos a visualizar los colores rojos, verde y azul 
 * alimentando para cada color una sola parte gracias al uso de 
 * pines PWM de la placa de Arduino.
 * 
 * @author Miguel Ángel Abellán
 * @company Programo Ergo Sum
 * @license Creative Commons. Reconocimiento CompartirIgual 4.0
 */

// Definimos las variables de tipo entero
int ledPinR = 9;
int ledPinG = 6;
int ledPinB = 5;
int delayTime = 1000;

//Este código se ejecuta la primera vez
void setup() {
  // Configuramos los pines en modo salida
  pinMode(ledPinR, OUTPUT);
  pinMode(ledPinG, OUTPUT);
  pinMode(ledPinB, OUTPUT);
  // Inicializamos los pines a un valor BAJO
  analogWrite(ledPinR, 255);
  analogWrite(ledPinG, 255);
  analogWrite(ledPinB, 255);
}

//Este código se ejecuta en bucle repetidamente
void loop() {
  // Escribimos el valor 0 para encender el rojo
  analogWrite(ledPinR, 0);
  analogWrite(ledPinG, 255);
  analogWrite(ledPinB, 255);
  // Esperamos
  delay(delayTime);
  // Escribimos el valor 0 para encender el verde
  analogWrite(ledPinR, 255);
  analogWrite(ledPinG, 0);
  analogWrite(ledPinB, 255);
  // Esperamos
  delay(delayTime);
  // Escribimos el valor 0 para encender el azul
  analogWrite(ledPinR, 255);
  analogWrite(ledPinG, 255);
  analogWrite(ledPinB, 0);
  // Esperamos
  delay(delayTime);
}
```



---



<img src="http://i.creativecommons.org/l/by-sa/4.0/88x31.png" /><br>
Esta obra está bajo una licencia de [Creative Commons Reconocimiento-CompartirIgual 4.0 Internacional](https://creativecommons.org/licenses/by-sa/4.0/deed.es_ES).