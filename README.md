# Density-Based-Traffic-system
#define red1 13
#define yellow1 12
#define green1 11

#define red2 10
#define yellow2 9
#define green2 8

#define red3 7
#define yellow3 6
#define green3 5

#define red4 4

#define yellow4 3
#define green4 2

#define sensor1 14
#define sensor2 15
#define sensor3 16
#define sensor4 17
#define sensor5 18

#define yellowLightTime 2000
#define greenLightTime 5000
#define sensorCheckTime 5000

int line=0;

void setup()
{
for (int i = 0; i &lt; 14; i++)
{
pinMode(i, OUTPUT);
}
for(int i=14;i&lt;20;i++)
{
pinMode(i, INPUT_PULLUP);
}

// int tickEvent = t.every(2000, doSomething);
digitalWrite(red2, HIGH);
digitalWrite(red3, HIGH);
digitalWrite(red4, HIGH);
}

void loop()
{

if(digitalRead(sensor1) == 1)
line=0;
else if(digitalRead(sensor2) == 1)
line=1;
else if(digitalRead(sensor3) == 1)
line=2;
else if(digitalRead(sensor4) == 1)
line=3;
else if(digitalRead(sensor5) == 1)
line=4;

traffic(line);
line++;
if(line == 5)
line=0;
}

void traffic(int line)
{
switch(line)
{
case 0:
digitalWrite(red1, LOW);
digitalWrite(yellow1, LOW);
digitalWrite(green1, HIGH);
Delay(greenLightTime);

digitalWrite(green1, LOW);
digitalWrite(yellow1, HIGH);
Delay(yellowLightTime);

digitalWrite(yellow1, LOW);
digitalWrite(red1, HIGH);
break;

case 1:
digitalWrite(red2, LOW);
digitalWrite(yellow2, LOW);
digitalWrite(green2, HIGH);
Delay(greenLightTime);

digitalWrite(green2, LOW);
digitalWrite(yellow2, HIGH);
Delay(yellowLightTime);

digitalWrite(yellow2, LOW);
digitalWrite(red2, HIGH);
break;

case 2:
digitalWrite(red3, LOW);
digitalWrite(yellow3, LOW);
digitalWrite(green3, HIGH);
Delay(greenLightTime);

digitalWrite(green3, LOW);
digitalWrite(yellow3, HIGH);
Delay(yellowLightTime);

digitalWrite(yellow3, LOW);
digitalWrite(red3, HIGH);
break;

case 3:
digitalWrite(red4, LOW);
digitalWrite(yellow4, LOW);
digitalWrite(green4, HIGH);
Delay(greenLightTime);

digitalWrite(green4, LOW);

digitalWrite(yellow4, HIGH);
Delay(yellowLightTime);

digitalWrite(yellow4, LOW);
digitalWrite(red4, HIGH);
break;

case 4:
digitalWrite(red1, LOW);
digitalWrite(yellow1, LOW);
digitalWrite(green1, HIGH);
Delay(greenLightTime);

digitalWrite(green1, LOW);
digitalWrite(yellow1, HIGH);
Delay(yellowLightTime);

digitalWrite(yellow1, LOW);
digitalWrite(red1, HIGH);
break;
}
}

/* void doSomething()
{
if(digitalRead(strLight1))
{
digitalWrite(light1, HIGH);
}

else
{
digitalWrite(light1, LOW);
}

if(digitalRead(strLight2))
{
digitalWrite(light2, HIGH);
}

else
{
digitalWrite(light2, LOW);
}
}*/

void Delay(int Time)
{
for(int i=0;i&lt;Time;i++)
{
// t.update();
delay(1);
}
}
