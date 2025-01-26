```c
const int IRSensor = 9; // Pin connected to the IR sensor module
const int LED = 13;     // Pin connected to the LED

void setup() {
  
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

  // Check if the sensor detects motion
  if (sensorStatus == HIGH) 
  {
    // Motion not detected: Turn off the LED
    digitalWrite(LED, LOW);
    Serial.println("No Motion Detected");
  } 
  else 
  {
    // Motion detected: Turn on the LED
    digitalWrite(LED, HIGH);
    Serial.println("Motion Detected!");
  }

  // Small delay to reduce noise and improve stability
  delay(100);

}
```