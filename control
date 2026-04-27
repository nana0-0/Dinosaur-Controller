#include "Keyboard.h"

const int upButtonPin = A0;
const int downButtonPin = 5;

int previousUpState = HIGH;
int previousDownState = HIGH;

void setup() {
  pinMode(upButtonPin, INPUT_PULLUP);
  pinMode(downButtonPin, INPUT_PULLUP);
  Keyboard.begin();
}

void loop() {
  int upState = digitalRead(upButtonPin);
  int downState = digitalRead(downButtonPin);

  if (upState == LOW && previousUpState == HIGH) Keyboard.press(KEY_UP_ARROW);
  if (upState == HIGH && previousUpState == LOW) Keyboard.release(KEY_UP_ARROW);

  if (downState == LOW && previousDownState == HIGH) Keyboard.press(KEY_DOWN_ARROW);
  if (downState == HIGH && previousDownState == LOW) Keyboard.release(KEY_DOWN_ARROW);

  delay(50);

  previousUpState = upState;
  previousDownState = downState;
}
