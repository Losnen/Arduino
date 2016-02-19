

int vol_x = A0;
int vol_y = A1;
int xpos = 0;
int ypos = 0;
void setup() {
  pinMode(vol_x,INPUT);
  pinMode(vol_y,INPUT);
  Serial.begin(9600);
  

}

void loop() {
  xpos = analogRead(vol_x);
  ypos = analogRead(vol_y);

  Serial.print("X=");
  Serial.print(xpos);

  Serial.print("Y=");
  Serial.print(ypos);
  Serial.print("\n");

  delay(1000);
  }
