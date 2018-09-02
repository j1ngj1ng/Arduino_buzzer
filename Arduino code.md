
```
int piezo = 3;
int button = 5;

void setup() {
  pinMode(piezo, OUTPUT);
  pinMode(button, INPUT_PULLUP);
}

void loop() {
  if (digitalRead(button) == LOW) {
    for(int cnt = 0; cnt < 10; cnt++){
      for(int i = 100; i < 300; i++){
        tone(piezo, i);
        delay(10);
      }
      for(int i = 300; i >= 100; i--){
        tone(piezo, i);
        delay(10);
      }
    }
  
    noTone(piezo);
  }
}

/* 이건 왜 있는거지..오류난당..

for(int cnt = 0; cnt < 10; cnt++){
  for(int i = 100; i < 300; i++){
    tone(piezo, i);
    delay(10);
  }
  for(int i = 300; i >= 100; i--){
    tone(piezo, i);
    delay(10);
  }
}
  
noTone(piezo);*/
```
