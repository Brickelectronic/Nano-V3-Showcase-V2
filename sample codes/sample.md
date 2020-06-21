// Nano V3 Showcase V2 - Sample Code 1
// Proximity Sensor Switch on - Delayed switch off
//
// Author: Alexander Ehle ak brickelectronic
// Website: https://brickelectronic.de

int switch_1 = 2;	// Sensor Input 1
int switch_2 = 3;	// Sensor Input 2
int switch_3 = 4;	// Sensor Input 3
int switch_4 = 13;	// Sensor Input 4

int channel_1 = 5;
int channel_2 = 6;
int channel_3 = 7;
int channel_4 = 8;
int channel_5 = 9;
int channel_6 = 10;
int channel_7 = 11;
int channel_8 = 12;

int loadSwitchState1 = 0;
int loadSwitchState2 = 0;
int loadSwitchState3 = 0;
int loadSwitchState4 = 0;
int loadSwitchState5 = 0;

int switchState1 = 0;
int switchState2 = 0;
int swichtState3 = 0;
int switchState4 = 0;
int switchState5 = 0;

boolean controlState_1 = false;
boolean controlState_2 = false;
boolean controlState_3 = false;
boolean controlState_4 = false;
boolean controlState_5 = false;

// Delay 30sec = 30000ms
int delay_1 = 30000;

void setup() {
  // Init outputs and states
  pinMode(switch_1, INPUT);     // Proximity Switch Input 1
  pinMode(switch_2, INPUT);     // Proximity Swicht Input 2
  pinMode(switch_3, INPUT);     // Proximity Swicht Input 3
  pinMode(switch_4, INPUT);     // Proximity Swicht Input 4
  pinMode(switch_5, INPUT);     // Proximity Swicht Input 5

  pinMode(channel_1, OUTPUT);    // LED Output 1
  pinMode(channel_2, OUTPUT);    // LED Output 2
  pinMode(channel_3, OUTPUT);    // LED Output 3
  pinMode(channel_4, OUTPUT);    // LED Output 4
  pinMode(channel_5, OUTPUT);    // LED Output 5
  pinMode(channel_6, OUTPUT);    // LED Output 6    
  pinMode(channel_7, OUTPUT);    // LED Outpur 7
  pinMode(channel_8, OUTPUT);    // LED Output 8

  // Init Outputs to Low for "Off"
  digitalWrite(channel_1, LOW);
  digitalWrite(channel_2, LOW);
  digitalWrite(channel_3, LOW);
  digitalWrite(channel_4, LOW);
  digitalWrite(channel_5, LOW);
  digitalWrite(channel_6, LOW);
  digitalWrite(channel_7, LOW);
  digitalWrite(channel_8, LOW);
}

void loop() {

  // Sensor Channel 1 drives all Outputs
  if(switchState1 == 0 && digitalRead(switch_1) == HIGH)
  {
    switchState1 = 1;
    digitalWrite(channel_1, HIGH);
    digitalWrite(channel_2, HIGH);
    digitalWrite(channel_3, HIGH);
    digitalWrite(channel_4, HIGH);
    digitalWrite(channel_5, HIGH);
    digitalWrite(channel_6, HIGH);
    digitalWrite(channel_7, HIGH);
    digitalWrite(channel_8, HIGH);    
    delay(30000);
    digitalWrite(channel_1, LOW);
    digitalWrite(channel_2, LOW);
    digitalWrite(channel_3, LOW);
    digitalWrite(channel_4, LOW);
    digitalWrite(channel_5, LOW);
    digitalWrite(channel_6, LOW);
    digitalWrite(channel_7, LOW);
    digitalWrite(channel_8, LOW);
    switchState1 = 0;
  }
}
