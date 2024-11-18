## موضوع آزمایش:به حرکت درآوردن موتور الکتریکی

### گزارش کار

برای کنترل موتورهای الکتریکی با آردوینو، از ماژول‌های درایور مثل L298N استفاده می‌کنیم. این ماژول دو خروجی دارد و می‌تواند همزمان دو موتور DC را کنترل کند. سرعت موتور با تکنیک PWM و جهت چرخش آن با H-Bridge کنترل می‌شود.

---

### کد برنامه

```cpp
void setup() {
  for (int i = 8; i < 11; i++) {
    pinMode(i, OUTPUT);
    }
}

void loop() {
  digitalWrite(9, HIGH);  
  digitalWrite(8, LOW);
  analogWrite(10, HIGH);
  delay(1000);

  digitalWrite(9, LOW); 
  digitalWrite(8, HIGH);
  analogWrite(10, i);
  delay(1000);

  for (int i=0; i<256; i++) {  
  digitalWrite(9, HIGH);
  digitalWrite(8, LOW);
  analogWrite(10, i);
  delay(20);
  }
  delay(50);

  for (int i=0; i<256; i++) { 
  digitalWrite(9, LOW);
  digitalWrite(8, HIGH);
  analogWrite(10, i);
  delay(20);
  }
  delay(50);
}
```
---

### تصویر مدار

<div align="center">
<img src="/media/microprocessor_19.gif">
</div>
![pic micro](/pic/microprocessor_1.jpg)

---

### شماتیک مدار 

<br>

<div align="center">
<img src="/media/schematic_17.jpg" width="600px" height="500px">
</div>
![pic micro](/pic/schematic_1.jpg)
