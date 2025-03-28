guide:
1. download zip file
2. open your file in arduino ide
3. go to sketch -> include library -> include .zip library
4. choose downloaded zip file

working code example:
```
#include <IRHandler.h>

IRHandler irHandler(17, 3, 0x0B, 0x07);
void setup() {
  Serial.begin(115200);
  irHandler.begin();
}

void loop() {
  int status = irHandler.checkStatus();
  if (status == 1) {
    Serial.println("Programmed");
  }
  else if (status == 2) {
    Serial.println("Started");
  }
  else if (status == 3) {
    Serial.println("Stopped");
  }
}

```
