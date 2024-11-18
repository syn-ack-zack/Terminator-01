# Terminator-01
## 2024 Hackers Teaching Hackers Conference Badge

This project acts as [Open Interpreter 01 ESP32 Client](https://01.openinterpreter.com/client/esp32) compatible with the [01 light server](https://01.openinterpreter.com/server/light). 01 is described as a natural language voice interface for computers. Powered by an ESP32-C3-Mini, MAX98357A digital to analog converter (DAC), and a SPH0645LM4H I2S microphone 


### Badge Operation

On boot, the badge will attempt to connect to the 01 server using stored WiFi credentials and a 01 server address. If no information is stored or the connection fails then the default state will remain disconnected. One of three voice lines can be played by activating the touch capacitive teeth on the front of the badge. Additionally, the HTH logo located on the center of the sunglasses can act as an easy way to toggle wireless connectivity.

The badge can be communicated to over the USB serial interface, using a 115200 baud rate. Any serial monitor supporting a LF character will work for issuing serial comands. 

To configure WiFi connection details you can connect to the Badge SSID (T-1337-v#) and visit the captive portal at http://4.3.2.1. From here enter the SSID/Password to have the badge join the network, afterwards specifying the 01 server will attempt the connection. If successful the server address will be saved. 

These details can also be configured via the serial menu uplink commands. The 2nd menu option details how these function. The remaining three menu options refer to CTF challenges which a [walkthrough can be found for here](https://github.com/syn-ack-zack/Terminator-01/wiki). 

<img src="https://github.com/user-attachments/assets/0c7ddde7-e5e3-4b81-be90-c92fc486135f" width="400">
<img src="https://github.com/user-attachments/assets/1c9c4d36-c21b-43c0-87c1-8fe78597fe24" width="440">

<br>
<img src="https://github.com/user-attachments/assets/2d15a7d5-782f-4c7d-92b0-b816bd905a2e" width="450">



<img src="https://github.com/user-attachments/assets/9f96a232-e234-4259-bdf1-bf85da5bef5e" width="450">

### 01 Light Server Setup 

This ESP32 client is designed to work with the _light_ variant of the 01 server. 

Clone the 01 repository 
```
git clone https://github.com/OpenInterpreter/01.git
```
Run the 01 light server 
```
poetry run 01 --server light
```

To customize agent behavior, modify or fork the profiles located in ```software/source/server/profiles/```. You can then specify this profile via the --profile flag. Other [flags can be found here](https://01.openinterpreter.com/server/flags). The default setup uses an OpenAI API to power the LLM functionality, though a local option is also available. 

https://01.openinterpreter.com/setup/introduction
