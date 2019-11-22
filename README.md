Speed-fan - Управление скоросью куллера
==============

0. Оглавление
----------------
1. [English](#english)

1.1. [Folders](#folders1)

2. [Русский](#russian)

2.1. [Папки](#folders2)

<a name="english"></a>1. English
--------------------------------
<a name="folders"></a>1.1. Folders
----------------------------------
**Speed_fan/Speed_fan.ino** - Code file

Code
```c++
//-----------------------------
//Constant pins buttons and fan
//-----------------------------
const int Button1 = 11;
const int Button2 = 12;
const int Button3 = 13;
const int Fan = 3;

//-----------------------------
//Setting pins
//-----------------------------

void setup() {
  //Serial.begin(9600);//Debug
  pinMode (Button1, INPUT_PULLUP);
  pinMode (Button2, INPUT_PULLUP);
  pinMode (Button3, INPUT_PULLUP);
  pinMode (Fan, OUTPUT);
}

byte Speed;//Var speed fan

//-----------------------------
//Function scan button
//-----------------------------

byte Button()
{
  if (digitalRead (Button1) == LOW)
  {
    Speed = 0;
  }

  if (digitalRead (Button2) == LOW)
  {
    Speed = 100;
  }

  if (digitalRead (Button3) == LOW)
  {
    Speed = 255;
  }
  delay(10);
  return Speed;
}

//-----------------------------
//General loop
//-----------------------------

void loop()
{
  Button();
  analogWrite (Fan, Button());
  //-----------------------------
  //DEBUG
  //-----------------------------
  /*
    Serial.print("Speed ");
    Serial.println(Button());
    Serial.print("sign ");
    Serial.println(analogRead(A0));
  */
}
```

<a name="russian"></a>2. Русский
--------------------------------
<a name="russian"></a>2.1. Папки
------------------------------
**Speed_fan/Speed_fan.ino** - Файл с кодом

Код
```c++
//-----------------------------
//Выбор контактов поключения кнопок и кулера к ардуино
//-----------------------------
const int Button1 = 11;
const int Button2 = 12;
const int Button3 = 13;
const int Fan = 3;

//-----------------------------
//Настройка подключения
//-----------------------------

void setup() {
  //Serial.begin(9600);//Debug
  pinMode (Button1, INPUT_PULLUP);
  pinMode (Button2, INPUT_PULLUP);
  pinMode (Button3, INPUT_PULLUP);
  pinMode (Fan, OUTPUT);
}

byte Speed;//Var speed fan

//-----------------------------
//Функция для определения нажатий клавиш
//-----------------------------

byte Button()
{
  if (digitalRead (Button1) == LOW)
  {
    Speed = 0;
  }

  if (digitalRead (Button2) == LOW)
  {
    Speed = 100;
  }

  if (digitalRead (Button3) == LOW)
  {
    Speed = 255;
  }
  delay(10);
  return Speed;
}

//-----------------------------
//Основной цикл
//-----------------------------

void loop()
{
  Button();
  analogWrite (Fan, Button());
  //-----------------------------
  //Отладка
  //-----------------------------
  /*
    Serial.print("Speed ");
    Serial.println(Button());
    Serial.print("sign ");
    Serial.println(analogRead(A0));
  */
}
```
