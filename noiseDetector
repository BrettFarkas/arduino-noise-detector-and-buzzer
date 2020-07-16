#include <TrueRandom.h>
//This uses the TrueRandom Library

int speaker = 9; //the piezo buzzer on pin 9
int tone = 1500;

int sensorPin = 4;    //Microphone Sensor Pin
int sensorValue = 0;

long unsigned present = 0;
long unsigned past = 0;


int RandomQuack = 0;
int RandomRest = 0;
int VarQuack = 0;
int VarRest = 0;



/*
Quack = 200
quick = 100
with a 100 space between

*/

void setup () {

pinMode (speaker, OUTPUT);
Serial.begin(9600);
}

void loop ()
{
sensorValue = analogRead(sensorPin);    
Serial.println(sensorValue);
 
 
if (sensorValue<509){ // if the noise level is high
 
 

 
//-------------------------------
VarQuack = TrueRandom.random(0,2);  // assign a Random Quack  
if (VarQuack == 0){               // it will be either 100 or 200 in duration
 RandomQuack = 100;
 Serial.println("short Quack");
} else {
 RandomQuack = 250;
 Serial.println("Quack");
}

VarRest = TrueRandom.random(0,2);  // assign a Random Rest time between quacks
if (VarRest == 0){               // it will be 50 or 100
 RandomRest = 50;
} else {
 RandomRest = 100;
}

 
past = millis();

//----------------------------------
do{                                     // QUACK do/while loop
present = millis();

digitalWrite (speaker, HIGH);
delayMicroseconds (tone / 2);
digitalWrite (speaker, LOW);
delayMicroseconds (tone / 2);
tone = 1500;
tone = map(tone, 0, 1023, 1000, 5000);

} while (present - past < RandomQuack);          // a random QUACK duration

delay (RandomRest);                   // random delay between Quacks

//----------------------------------------------
// assign Random Values again
VarQuack = TrueRandom.random(0,2);  // assign a Random Quack  
if (VarQuack == 0){               // it will be either 100 or 200 in duration
 RandomQuack = 100;
 Serial.println("short Quack");
} else {
 RandomQuack = 200;
 Serial.println("Quack");
}

VarRest = TrueRandom.random(0,2);  // assign a Random Rest time between quacks
if (VarRest == 0){               // it will be 50 or 100
 RandomRest = 50;
} else {
 RandomRest = 100;
}

//------------------------------------
past = millis();

do{  // second random quack
present = millis();
 
digitalWrite (speaker, HIGH);
delayMicroseconds (tone / 2);
digitalWrite (speaker, LOW);
delayMicroseconds (tone / 2);
tone = 1500;
tone = map(tone, 0, 1023, 1000, 5000);

} while (present - past < RandomQuack);     // another random quack duration
//-------------------------------------

delay (RandomRest);                   // delay between quack


//----------------------------------------------
// assign Random Values again
VarQuack = TrueRandom.random(0,2);  // assign a Random Quack  
if (VarQuack == 0){               // it will be either 100 or 200 in duration
 RandomQuack = 100;
 Serial.println("short Quack");
 Serial.println(" ");
} else {
 RandomQuack = 200;
 Serial.println("Quack");
 Serial.println(" ");
}

VarRest = TrueRandom.random(0,2);  // assign a Random Rest time between quacks
if (VarRest == 0){               // it will be 50 or 100
 RandomRest = 50;
} else {
 RandomRest = 100;
}
//-------------------------------------------


past = millis();

do{  // Third random quack
present = millis();
 
digitalWrite (speaker, HIGH);
delayMicroseconds (tone / 2);
digitalWrite (speaker, LOW);
delayMicroseconds (tone / 2);
tone = 1500;
tone = map(tone, 0, 1023, 1000, 5000);

} while (present - past < RandomQuack);     // another random quack duration
//-------------------------------------

delay (RandomRest);                  

delay(1000);

} else {
 digitalWrite(speaker, LOW);
}


}
