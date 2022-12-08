/*
การต่ออุปกรณ์ สามารถอ่านเพิ่มได้ที่ Link : https://www.ab.in.th/b/12
*/

int LedRED = 12;
int LEDgreen = 11;
int smokeA0 = A0;

int sensorThres = 400;  //ตั้ง ค่าความหนาของตวัน แก๊ส ก๊าซที่ 400

void setup() {
  Serial.begin(9600);
  pinMode(LedRED, OUTPUT);
  pinMode(LEDgreen, OUTPUT);
  pinMode(smokeA0, INPUT);
}

void loop() {
  int analogSensor = analogRead(smokeA0);
  Serial.print("Pin A0: ");
  Serial.println(analogSensor); 

  if (analogSensor > sensorThres)  {
    digitalWrite(LedRED, HIGH);
    digitalWrite(LEDgreen, LOW);
  }

  else  {
    digitalWrite(LedRED, LOW);
    digitalWrite(LEDgreen, HIGH);
  }
  delay(100);
}
