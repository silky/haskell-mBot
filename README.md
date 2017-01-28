# MBot robot library

With this library it is possible to control the mBot robot from within Haskell over 2.4ghz wireless.
The mBot itself needs to contain the standard firmware otherwise the library will not behave as expected. 
There is support for steering the motors and leds and for reading the linesensor and the ultrasonic sensor.
An small example program is shown below, for more information about the individual functions take a look at the api documentation below.

```Haskell
import MBot

main =  do
  putStrLn "My first mBot program in Haskell !"
  -- Open the connection with the mMbot
  d <- openMBot
  putStrLn "Opened a connection with the mBot"
  -- Turn on led 1 of the mBot and set the RGB value to (0,100,0)
  sendCommand d $ setRGB 1 0 100 0
  putStrLn "Look at all the pretty colors !"
  -- Turn on led 2 of the mBot and set the RGB value to (100,0,0)
  sendCommand d $ setRGB 2 100 0 0 
  -- close the connection with the mBot 
  closeMBot d
```
