int ledPins[] = {2,3,4,5,6,9,10,11};
String readString;

void setup() {
  Serial.begin(9600);

int index;

// In this sketch, we'll use "for() loops" to step variables from

// one value to another, and perform a set of instructions for

// each step. For() loops are a very handy way to get numbers to

// count up or down.

// Every for() loop has three statements separated by

// semicolons (;):

// 1. Something to do before starting

// 2. A test to perform; as long as it's true, keep looping

// 3. Something to do after each loop (increase a variable)

// Here we'll use a for() loop to initialize all the LED pins

// to outputs. This is much easier than writing eight separate

// statements to do the same thing.

// This for() loop will make index = 0, then run the pinMode()

// statement within the brackets. It will then do the same thing

// for index = 2, index = 3, etc. all the way to index = 7.

for(index = 0; index <= 8; index++)

{

pinMode(ledPins[index],OUTPUT);

// ledPins[index] is replaced by the value in the array.

// For example, ledPins[0] is 2

}

}



void loop() {
  while (Serial.available()) {
    delay(3);  
    char c = Serial.read();
    readString += c; 
  }
  if (readString.length() >0) {
    Serial.println(readString);
    if (readString == "on")     
    {
      digitalWrite(ledPins[0], HIGH); //Turns on LED #0 (pin 2)

      digitalWrite(ledPins[1], HIGH); //Turns on LED #1 (pin 3)

      digitalWrite(ledPins[2], HIGH); //Turns on LED #2 (pin 4)

      digitalWrite(ledPins[3], HIGH); //Turns on LED #3 (pin 5)

      digitalWrite(ledPins[4], HIGH); //Turns on LED #4 (pin 6)

      digitalWrite(ledPins[5], HIGH); //Turns on LED #5 (pin 9)

      digitalWrite(ledPins[6], HIGH); //Turns on LED #6 (pin 10)

      digitalWrite(ledPins[7], HIGH); //Turns on LED #7 (pin 11)
   
    }
    if (readString == "off")
    {
      digitalWrite(ledPins[0], LOW); //Turns on LED #0 (pin 2)

      digitalWrite(ledPins[1], LOW); //Turns on LED #1 (pin 3)

      digitalWrite(ledPins[2], LOW); //Turns on LED #2 (pin 4)

      digitalWrite(ledPins[3], LOW); //Turns on LED #3 (pin 5)

      digitalWrite(ledPins[4], LOW); //Turns on LED #4 (pin 6)

      digitalWrite(ledPins[5], LOW); //Turns on LED #5 (pin 9)

      digitalWrite(ledPins[6], LOW); //Turns on LED #6 (pin 10)

      digitalWrite(ledPins[7], LOW); //Turns on LED #7 (pin 11)
    }
    readString="";
  } 
}
