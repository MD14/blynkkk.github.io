
### Step Control

Step control is like 2 buttons assigned to 1 pin. One button increments your value by desired step and another 
one decrements it. It is very useful for use cases where you need to change your values very precisely and you can't 
achieve this precision with slider widget.

**Send Step** option allows you to send step to hardware instead of actual value of step widget.
**Loop value** option allows you to reset step widget to start value when maximum value is reached.

You can change step state from hardware side. For example : 

```cpp
Blynk.virtualWrite(V1, val);
```

You can change step labels from hardware with : 

```cpp
Blynk.setProperty(V1, "label", "My Stepper");
```

or change color : 

```cpp
//#D3435C - Blynk RED 
Blynk.setProperty(V1, "color", "#D3435C");
```

You can also get step control state from server in case your hardware was disconnected with Blynk Sync feature : 

```cpp
BLYNK_CONNECTED() {
  Blynk.syncVirtual(V1);
}

BLYNK_WRITE(V1) {
  int stepperValue = param.asInt();
}
```

**Sketch:** [Basic Sketch](https://github.com/blynkkk/blynk-library/blob/master/examples/GettingStarted/BlynkBlink/BlynkBlink.ino)