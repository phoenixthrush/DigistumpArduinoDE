DigistumpArduino - Germanized Keyboard Library
================

This fork adds only a single file to enable DigiKeyboard usage for keyboards with german layout
```c
//This the important part, include the De suffixed version instead of the normal one and the rest goes same as the original lib.
#include "DigiKeyboardDe.h"

void setup() {
  // don't need to set anything up to use DigiKeyboard
}


void loop() {
  // this is generally not necessary but with some older systems it seems to
  // prevent missing the first character after a delay:
  DigiKeyboardDe.sendKeyStroke(0);
  
  DigiKeyboardDe.println("Hello XYZ !\"§$%&/()=? [] {}!");
  // It's better to use DigiKeyboard.delay() over the regular Arduino delay()
  // if doing keyboard stuff because it keeps talking to the computer to make
  // sure the computer knows the keyboard is alive and connected
  DigiKeyboard.delay(5000);
}
```