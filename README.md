 
       _  ______      _    _  _______ _   _       _ ____      ___ ___ _____ 
      | |/ /  _ \    / \  | |/ / ____| \ | |     | |  _ \    |_ _/ _ \_   _|
      | ' /| |_) |  / _ \ | ' /|  _| |  \| |  _  | | |_) |    | | | | || |  
      | . \|  _ <  / ___ \| . \| |___| |\  | | |_| |  _ < _   | | |_| || |  
      |_|\_\_| \_\/_/   \_\_|\_\_____|_| \_|  \___/|_| \_(_) |___\___/ |_|  
      
                           KJR 3 WIRE PROTOCOL 
                        https://krakenjriot.tech/
                   https://internetofthingsbuilder.com/
                           funsideofwine@gmail.com   
 
                   Copyright (c) 2020 Rolly Falco Villacacan 
 
 
 **KJR 3-Wire-Protocol**
 
 **The techinical aspect behind the inner working of the kjr-3-wire-protocol and why it works well!**
 - It uses electrical energy pulses (pulse of certain duration)
 - Electrical energy travels at a constant speed no matter the medium (wire) resistance is
 - This protocol is similar to morse code, it depends on the duration of the beeps
 - This works on Master / Slaves topoloy (The master will initiate the call to specific slaves and the slaves that was called will respond to the master in return)
 
 **Advantages**
 - Eliminated the distance limitations of common wire communication protocols (i.e. I2C, RS-232 (Serial), Parallel, & etc.)
 - Very easy to setup and implement
 - You can add as many slaves as you want as long as you can accept the added delays for each slaves as this protocol works on queue concept as well
 - Immune to cross talk electromagnetic interference since its using low frequency transmission protocol
 
 **Disadvantages**
 - Slow transfer as this method of detection depends on the duration of the pulses
 - Voltage drop along the wires is directly proportional to the distance, if your project will require only few hundred meters that would not be an issue, if you wanted to implement this at a larger distances, you can still make this work, just keep and maintain the voltage at the recieving end at a allowable detection threshold, you can use an external power booster

*The flow of communication is pretty basic*
1. the MASTER initiates the request by putting the SIGNAL LINE to HIGH
2. when SIGNAL LINE went high all SLAVES listen
3. the MASTER send a string of this format "1,xxxxx" or "2,xxxx" to the MASTER LINE (the number denotes the SLAVE ID the MASTER wants to communicate with)
4. All SLAVES receives the data
5. the MASTER now will put the SIGNAL LINE to LOW, this signals all SLAVEs that they can send data now to MASTER to the SLAVE LINE.
6. Only one SLAVE will respond, That one that matches the SLAVE ID the MASTER sent  "x-" 


**Note**
- The current version has a 16 character sets only ( Dot { } 0 1 2 3 4 5 6 7 8 9 + - Comma ) feel free to add/modify the source code
- Use COMMON GROUND LINE if you will be using a separate power source for each or one of your microcontroller

 **See below sample layout connections** 
 
 <img src="https://github.com/krakenjriot/KJR_3-Wire_Protocol/blob/master/sample_layout_connections.png" width=800 />  
 
  **Sample Transmission for 1 master and two slave nodes @100meters Fig.2** 
  
 <img src="https://github.com/krakenjriot/KJR_3-Wire_Protocol_v1.02/blob/master/SAMPLE_TRANSMISSION.PNG" width=800 />  
 Fig.2
</br>
</br>
**How to add "kjr3wire" repository as Arduino Library?**
Follow below steps..
- Download zip copy of the repository 
*Clone or Download --> click Download ZIP
<img src="https://github.com/krakenjriot/KJR_3-Wire_Protocol_v1.02/blob/master/images/image1.PNG" width=800 /> 


- Save the file to your Arduino Library or (any folder will work just don't forget where it is) 
*Click Save button to complete the download process
<img src="https://github.com/krakenjriot/KJR_3-Wire_Protocol_v1.02/blob/master/images/image2.PNG" width=800 /> 

- Open Arduino IDE
*Click Sketch --> Include Library --> Add ZIP Library --> find the downloaded file
<img src="https://github.com/krakenjriot/KJR_3-Wire_Protocol_v1.02/blob/master/images/image3.PNG" width=800 /> 

- In the Arduino IDE
*Find the downloaded file, select and finally click Open to complete the import
<img src="https://github.com/krakenjriot/KJR_3-Wire_Protocol_v1.02/blob/master/images/image4.PNG" width=800 /> 

- In the Arduino IDE (COMPLETED!)
To Test your first kjr3wire sketch, 
*Click File --> Example --> and scroll below --> find the newly import library --> select the sample and compile
<img src="https://github.com/krakenjriot/KJR_3-Wire_Protocol_v1.02/blob/master/images/image5.PNG" width=800 /> 

**Steps Finished


**To get the latest updates and news, see below links**
- Facebook Group: https://www.facebook.com/groups/krakenjr
- Github: https://github.com/krakenjriot/
- Website: https://internetofthingsbuilder.com
- Website: https://krakenjriot.tech
