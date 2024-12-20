# スイッチ

## 🌟 概要

押されたか押されていないかを検知するセンサーです。

## 🌟 配線

基板上のスイッチの端子に接続します。極性はありません。

![alt text](<Photo 2024-12-21, 11 41 00.jpg>)

## 🌟 ファームウエア

digitalRead() 関数を使ってスイッチの状態を読み取ります。押されていないときに入力電圧が不安定にならないようにプルアップします。

押すとグランドに接続されるので、押されたときに LOW になります。

```cpp
const int pin = 2;  // スイッチのピン番号

void setup()
{
    Serial.begin(115200);
    pinMode(pin, INPUT_PULLUP);
}

void loop()
{
    const bool isPressed = digitalRead(pin) == LOW;

    Serial.println(isPressed);

    delay(10);
}
```
