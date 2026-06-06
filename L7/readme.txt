---Utilització---
Els controls consten de 4 botons: les 4 direccions cardinals (esquerre, dreta, dalt, baix) i el botó de confirmació (ok).
Els botons estan col·locats en forma de creueta en el Proteus pel seu ús intuïtiu, el botó de confirmar està just a sota la creueta.

Alternativament es pot controlar per terminal de la següent manera:
dalt - w
esquerra - a
baix - s
dreta - d
confirmar - e

S'ha decidit dissenyar una versió alternativa per la navegació de menús que hauria de ser molt intuïtiva per l'usuari:
Des del menú principal es podria accedir a tres submenús:
- Configuració Hora.
- Configuració Rentadora (amb esquerra i dreta alternem entre funcionalitats).
- Iniciar Rentat (amb esquerra i dreta alternem amb visualització de temperatura).
De totes maneres es pot trobar adjunt un diagrama amb la navegació de menús.


---Característiques---
Totes les funcionalitats demanades a l'enunciat s'han implementat amb èxit.
A continuació s'expliquen modificacions i/o altres funcionalitats del projecte:
 - Com s'ha esmentat a la secció anterior, la navegació de menús ha sigut modificada i adaptada per una experiència més còmode per a l'usuari.
 - S'ha implementat 

---Implementació tècnica---
S'ha optat per una implementació modular, això permet la possible expansió del projecte en un futur sense impedir que les funcionalitats ja implementades deixen de funcionar.

Per una banda, diferents mòduls implementen funcionalitats aïllades del projecte (comunicació USART, convertidor ADC, botons, rellotge, PWM, washer, GLCD).
Per altra banda el mòdul 'ui' implementa funcions auxiliars d'escriptura per la pantalla GLCD.
Finalment, la unió entre la lògica i l'escriptura per pantalla es fa principalment en el mòdul 'Screen', un dels fitxers més importants del projecte.

En el main s'inicialitzen tots els mòduls, es defineix la funció de la rutina del servei a la interrupció i s'implementa el bucle principal:
1. Es llegeix l'entrada de l'usuari.
2. S'executa la lògica segons l'entrada i la pantalla.
3. S'actualitza la sortida per pantalla segons la lògica executada.