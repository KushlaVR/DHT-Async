# DHT-Async

This lib is equel to DHT with only diference - it have readAsync() method

##How to use
1. copy DHT-Async files into Scetch folder
2. Add include statement to scetch 
>#include "DHT_Async.h"
3. declare DHT sensor 
>DHTAsync dht;
3. Setup pin
```
voud setup(){
    ...
    ...
    dht.setup(DHTPin, DHTtype);
}
```
4. Call DHT.readAsync() in the end of the loop()
```
void loop() {
    ...
    ...
    dht.readAsync();
    if (dht.isReady()){
        Serial.printf("Temp=%i; hum=%i\n", dht.getTemperature(), dht.getHunidity());
    }
}
```

The library will read temp+hum avry 2 cecond without blocking loop(). 
getTemperature() function - returns last readed temp
getHunidity() function - returns last readed humidity
isReady() - return true if library already ever read the data from DHT sensor.
