/********************************************************************
* Accionamento dunha lámpara mediante unha fonte de alimentación 
* a 24vCC conectada ao pin 11. Esta solo se activará cando o led do pin 12 estea activo,
* tamén estará desactivado dependendo novamente do estado do pin 12.
* Añadese un pulsador ao pin 10 que ao pulsar ao final de cada ciclo paraliza a secuencia e ao soltar esta continua.
* Autor: Javi Figueiro
* Data: 13/12/23
********************************************************************/

// C++ code
//

//Declaramos como bool(0e1) o pulsador.
bool pulsador;

void setup()
{
  pinMode(LED_BUILTIN, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(10, INPUT);
}

void loop()
{
  //Creamos a variable para o pulador.
  pulsador = digitalRead(10);
  //si pulsamos inhabilita,senon segue a secuencia.
  if(!pulsador) {
  //Encende o led pin trece 4 seconnds.  
  digitalWrite(LED_BUILTIN, HIGH);
  delay(4000); // Wait for 4000 millisecond(s)
  //Apagase o led do pin 13 2  segundos.
  digitalWrite(LED_BUILTIN, LOW);
  delay(2000); // Wait for 2000 millisecond(s)
  //arranca o led do pin 12 e a lámpada do 11 4 segundos.
  digitalWrite(12, HIGH);
  digitalWrite(11, HIGH);
  delay(4000); // Wait for 4000 millisecond(s)
  //apagase o led do pin 12 e a lámpara do pin 11 dous seconds.
  digitalWrite(12, LOW);
  digitalWrite(11, LOW);
  delay(2000); // Wait for 2000 millisecond(s)
}
  else if(pulsador){
    delay(500);
  }
}
