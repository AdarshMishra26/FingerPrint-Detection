# Adafruit Fingerprint Sensor Library

This is a library for interfacing with the Adafruit optical Fingerprint sensor. The sensor is designed to work with TTL Serial communication, requiring only 2 pins to interface.

## Introduction

This library provides a set of functions to communicate with the Adafruit Fingerprint sensor. It allows users to perform various operations such as enrolling fingerprints, searching for matching fingerprints, storing and deleting fingerprint templates, and controlling the built-in LED and Aura LED (if available).

## Getting Started

To use this library, you'll need to connect the Adafruit Fingerprint sensor to your microcontroller using TTL Serial communication. You can use either Hardware Serial or Software Serial depending on your platform. Ensure that you have the necessary dependencies installed and that you include the library in your project.

## Features

- Verify password
- Get sensor parameters
- Capture fingerprint image
- Convert image to feature template
- Create fingerprint model
- Store fingerprint model
- Load fingerprint model
- Get fingerprint template
- Delete fingerprint model
- Empty database
- Search for fingerprints
- Get template count
- Set password
- Control built-in LED
- Control Aura LED (if available)

## Usage

1. Include the library in your project.
2. Initialize the sensor with either Hardware Serial or Software Serial.
3. Begin communication with the sensor using the `begin()` function.
4. Perform desired operations using the provided functions.

## Example

```cpp
#include <Adafruit_Fingerprint.h>

#define FINGERPRINT_RX_PIN 2
#define FINGERPRINT_TX_PIN 3

SoftwareSerial mySerial(FINGERPRINT_RX_PIN, FINGERPRINT_TX_PIN);
Adafruit_Fingerprint finger = Adafruit_Fingerprint(&mySerial);

void setup() {
  Serial.begin(9600);
  delay(100);
  finger.begin(57600);

  if (finger.verifyPassword()) {
    Serial.println("Found fingerprint sensor!");
  } else {
    Serial.println("Did not find fingerprint sensor :(");
    while (1) {
      delay(1);
    }
  }
}

void loop() {
  // Perform fingerprint operations here
}
```


## License

This library is released under the BSD license. Please see the [license file](LICENSE) for more details.
```
