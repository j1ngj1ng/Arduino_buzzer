# Arduino_Buzzer

 제목    : 피에조 부저 (Piezo Buzzer)  사이렌 소리
 내용   : 스위치를 누를 때마다, 사이렌 소리를 내도록 만들어 봅니다.

피에조 부저를 3번 핀, 버튼을 5번 핀으로 설정한다.

스위치가 연결된 핀의 모드를 INPUT_PULLUP 상태(초기 로직레벨을 HIGH로 설정)로 설정합니다.  설정된 디지털 핀은 아래와 같은 값을 반환합니다.

스위치가 열려있다면 **(누르지 않은 상태) HIGH**
스위치를 닫혀있다면 **(누른 상태), LOW**

피에조 부저의 tone을 100-->300 이동하며 이를 10번 반복한다.

  



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
```
