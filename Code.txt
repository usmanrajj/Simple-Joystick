/*
Rajj YT 
Full vedio available on Youtube :-
https://youtu.be/XiCqwNTc_mQ

Circuit diagram :-\
https://github.com/usmanrajj/Simple-Joystick
*/
int xpin = A0;            // Connect RVx pin with Analog Pin A0
int ypin = A1;            // Connect RVx pin with Analog Pin A1
int sw = 2;               // Connect sw pin with Digital pin 2
void setup(){
  Serial.begin(9600);       // Initialize Serial Monitor
  pinMode(xpin,INPUT);      // Rvx-pin act as Input
  pinMode(ypin,INPUT);      // Rvy-pin act as Input
  pinMode(sw,INPUT);        // Button act as Input
  digitalWrite(sw,HIGH);    // Turn on pin to take Information
}
void loop(){
  int x_axis=analogRead(xpin);        // Store y Coordinates in y_axis variable
  int y_axis=analogRead(ypin);        // Store x Coordinates in x_axis variable
  int button_state=digitalRead(sw);   // Store Button condition in Button_state variable
// Display
  Serial.print("X-Axis : ");
  Serial.print(x_axis);
  Serial.print("   ");
  Serial.print("Y-Axis : ");
  Serial.print(y_axis);
  Serial.print("   ");
  Serial.print("Button State : ");
  Serial.println(button_state);       // 0 mean Pressed , 1 mean Released 
  delay(100);                         // Wait for 100mili second to show again data
}