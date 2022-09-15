int t=2;
int e=3;
void setup()
{
  Serial.begin(9600);
  pinMode(t,OUTPUT);
  pinMode(e,INPUT);
  pinMode(13,OUTPUT);
  pinMode(8,OUTPUT);
}
void loop()
{
  int p=digitalRead(4);
  Serial.println(p);
  if(p)
  {
    digitalWrite(13,HIGH);
    Serial.println("motion detected and led on!!");
  }
  else
    digitalWrite(13,LOW);
  digitalWrite(t,LOW);
  digitalWrite(t,HIGH);
  delayMicroseconds(10);
  digitalWrite(t,LOW);
  float dur=pulseIn(e,HIGH);
  float dis=(dur*0.0343)/2;
  Serial.print("Distance : ");
  Serial.println(dis);
  Serial.println(" cm");
  if(dis<100)
    digitalWrite(8,HIGH);
  else
    digitalWrite(8,LOW);
}
  
