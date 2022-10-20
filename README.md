# ArduinoDeltaTime
 the Tiny Time Sharing System without interrupts
  
# How to use  
```
#include <Arduino.h>
#include "tmDeltaTime.h"
  :
TmDeltaTime* pTdt= new TmDeltaTime(); // new or TmDeltaTime tdt;

void evCntA(uint32_t deltaTime){
      // execute every 5 seconds
}
void evCntB(uint32_t deltaTime){
      // execute every 0.1 seconds
}
    :
void setup() {
  pTdt->Setup(); // setup tmDeltaTime (a Tiny Time Sharing System)
  pTdt->AddTrig(evCntA,5000); // call evCntA() every 5 seconds.
  pTdt->AddTrig(evCntB,100); // call evCntB() every 0.1 seconds.
    :
}

void loop() {
  pTdt->Update(); // call in loop()
  delay(10); // Larger than minimum interval time in pTdt->AddTrig().
}
```  
[日本語版](https://qiita.com/ELIXIR/items/66435fdd357d664068e8)
