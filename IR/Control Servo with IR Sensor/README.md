```c
#include <Servo.h>

// Create servo object to control a servo
// Twelve servo objects can be created on most boards
Servo myservo;

// Variable to store the servo position
int pos = 0;

const int IRSensor = 9; // Pin connected to the IR sensor module
const int LED = 13;     // Pin connected to the LED

void setup() {
  
    // Attaches the servo on pin 8 to the servo object

  myservo.attach(8);

  // Initialize serial communication for debugging
  Serial.begin(9600);
  Serial.println("Serial Communication Initialized");

  // Configure the pin modes
  pinMode(IRSensor, INPUT); // Set IR sensor pin as INPUT
  pinMode(LED, OUTPUT);     // Set LED pin as OUTPUT

  // Turn off the LED initially
  digitalWrite(LED, LOW);
  Serial.println("System Ready");

}

void loop() {
  
  // Read the status of the IR sensor
  int sensorStatus = digitalRead(IRSensor);

  Serial.println(sensorStatus);

  myservo.write(180); // Set to 180 degrees

  // Check if the sensor detects motion
  if (sensorStatus == HIGH) 
  {
    // Motion not detected: Turn off the LED
    digitalWrite(LED, LOW);

    myservo.write(0); // Set to 0 degrees

    Serial.println("No Motion Detected");
  } 
  else 
  {
    // Motion detected: Turn on the LED
    digitalWrite(LED, HIGH);
    
    myservo.write(180); // Set to 180 degrees

    Serial.println("Motion Detected!");
  }

  // Small delay to reduce noise and improve stability
  delay(100);

}
```