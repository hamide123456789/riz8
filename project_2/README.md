## هدف آزمایش اندازه گیری دما به صورت آنالوگ 

### گزارش کار
سنسور LM35 دمای محیط را به صورت آنالوگ اندازه‌گیری می‌کند، در حالی که سنسور DHT11 دما را به صورت دیجیتالی می‌سنجد.

---

### کد برنامه

```cpp
int lm35 = A0;
int led = 10;

void setup() {
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int sensorValue = analogRead(lm35);
  float voltage = sensorValue * (5.0 / 1023.0);
  float temperature = voltage * 100;
  if (temperature > 26) {
    digitalWrite(led, HIGH);
    } else {
      digitalWrite(led, LOW);
      }

    Serial.print("Temp = ");
    Serial.print(temperature);
    Serial.println(" *C");
    delay(1000);
}
```

### تصویر مدار

![pic micro](/pic/microprocessor_2.jpg)

---

### شماتیک مدار 

![pic schematic](/pic/schematic_2.jpg)


