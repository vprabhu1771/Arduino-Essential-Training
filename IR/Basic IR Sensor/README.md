
```
https://www.youtube.com/watch?v=Wj9KBcNQwaA
```

```c
const int IRSensor = 9; // Pin connected to the IR sensor module

void setup() {
  
  // Initialize serial communication for debugging
  Serial.begin(9600);
  Serial.println("Serial Communication Initialized");

  // Configure the pin modes
  pinMode(IRSensor, INPUT); // Set IR sensor pin as INPUT

}

void loop() {
  
  // Read the status of the IR sensor
  int sensorStatus = digitalRead(IRSensor);

  Serial.println(sensorStatus);

  delay(300);

}
```