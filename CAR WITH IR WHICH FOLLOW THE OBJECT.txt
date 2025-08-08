#include <AFMotor.h>

// Motor setup
AF_DCMotor motor1(1);  // Back Left
AF_DCMotor motor2(2);  // Back Right
AF_DCMotor motor3(3);  // Front Left
AF_DCMotor motor4(4);  // Front Right

// IR sensor pins
int middleSensor = A0;


void setup() {
  Serial.begin(9600);

  // Set motor speeds
  motor1.setSpeed(130);
  motor2.setSpeed(130);
  motor3.setSpeed(130);
  motor4.setSpeed(130);

  // Set IR sensor pins
  pinMode(middleSensor, INPUT);
 
}

void loop() {
  // Read analog values
  int midVal   = analogRead(middleSensor);
 

  Serial.print("Middle: "); Serial.print(midVal);
 

  int threshold = 500;  // Adjust based on testing

  bool midDetected   = midVal < threshold;
 

  // Logic
  if (midDetected) {
    moveForward();
  }
  else {
    stopMotors();
  }

  delay(100); // Small delay
}

// === Motor Control Functions ===

void moveForward() {
  motor1.run(FORWARD);
  motor2.run(FORWARD);
  motor3.run(FORWARD);
  motor4.run(FORWARD);
}

void stopMotors() {
  motor1.run(RELEASE);
  motor2.run(RELEASE);
  motor3.run(RELEASE);
  motor4.run(RELEASE);
}
