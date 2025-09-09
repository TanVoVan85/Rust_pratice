# Rust_pratice
This is for rust programming pratice
Simulate led toggle with Wowki simulate adding bellow text to diagram json

{
  "version": 1,
  "author": "Vo Tan",
  "editor": "wokwi",
  "parts": [
    {
      "type": "board-esp32-devkit-c-v4",
      "id": "esp",
      "top": 0,
      "left": 0,
      "attrs": { "builder": "rust-nostd-esp" }
    },
    { "type": "wokwi-led", "id": "led1", "top": 63.6, "left": 205.4, "attrs": { "color": "red" } },
    {
      "type": "wokwi-resistor",
      "id": "r1",
      "top": 138.35,
      "left": 153.6,
      "attrs": { "value": "1000" }
    }
  ],
  "connections": [
    [ "esp:TX", "$serialMonitor:RX", "", [] ],
    [ "esp:RX", "$serialMonitor:TX", "", [] ],
    [ "led1:C", "esp:GND.2", "green", [ "v0" ] ],
    [ "led1:A", "r1:2", "green", [ "v0" ] ],
    [ "r1:1", "esp:2", "green", [ "v0" ] ]
  ],
  "serialMonitor": { "display": "terminal", "convertEol": true },
  "dependencies": {}
}
Connect wiring to PIN GPIO 2 on ESP32, using esp HAL library to control toggle led with delay time 
<img width="695" height="651" alt="image" src="https://github.com/user-attachments/assets/2ac62352-181b-4eab-9628-5676a87ce5c4" />
