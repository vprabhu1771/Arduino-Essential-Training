The output you're seeing on the serial monitor, which appears as garbled text (e.g., "��������������"), usually indicates a mismatch between the baud rate configured in your Arduino code and the baud rate set in the serial monitor. To resolve this issue, follow these steps:

### 1. Check and Match the Baud Rate:
- Ensure that the `Serial.begin(115200);` in your Arduino code matches the baud rate selected in the Arduino IDE's **Serial Monitor**. 
- In this case, select **115200 baud** from the dropdown menu at the bottom right of the Serial Monitor.

### 2. Upload the Code Again:
- After confirming the baud rate in the Serial Monitor, re-upload the code to the Arduino board.
- Open the Serial Monitor immediately after uploading to ensure proper communication.

### 3. Ensure the Correct Board and Port:
- Verify that the correct board and COM port are selected in the Arduino IDE (**Tools > Board** and **Tools > Port**).

### 4. Verify Serial Monitor Encoding:
- Ensure the Serial Monitor encoding is set to "No Line Ending" or the appropriate setting that matches your communication style.

### 5. Hardware Check:
- Confirm that the IR sensor is connected properly:
  - The **signal pin** should be connected to **pin 9** on the Arduino.
  - The **VCC** and **GND** pins of the sensor should be properly powered.

### Testing:
Once these steps are completed, the Serial Monitor should display `1` (for no obstacle) or `0` (for an obstacle detected) every 300 milliseconds, as expected from your code.

If the issue persists after ensuring all of the above, let me know, and we can further troubleshoot!