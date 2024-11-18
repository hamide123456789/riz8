## هدف آزمایش کنترل سرعت موتور DC

### گزارش کار

برای کنترل موتورهای الکتریکی با آردوینو، از ماژول‌های درایور موتور مثل L298N استفاده می‌شود که قابلیت تنظیم دو موتور DC به صورت همزمان را دارد. برای کنترل کامل موتور DC، از تکنیک PWM برای سرعت و از H-Bridge برای جهت چرخش استفاده می‌کنیم

---

### کد برنامه

```cpp
int power = 0;

void setup() {
  for (int i = 8; i < 11; i++) {
    pinMode(i, OUTPUT);
    }
}

void loop() {
  power = analogRead(A3);
  int hashVal = map(power, 0, 1023, 0, 255);
  digitalWrite(8, LOW);
  digitalWrite(9, HIGH);
  analogWrite(10, hashVal);
  delay(100);
}
```

---

### تصویر مدار 


![pic micro](/pic/microprocessor_3.jpg)

---

### شماتیک مدار 


![pic schematic](/pic/schematic_3.jpg)

