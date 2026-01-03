<img width="1920" height="1080" alt="image" src="https://github.com/GaneshKishore01/Smart-Hydroponics-PCB/blob/main/src/centre.png" />#
A PCB(Printed-Circuit-Board) designed for automation of small scale hydroponics.
# **Description**

## **What it is**
A ready-to-use printed circuit board capable of measuring pH, TDS, temprature & humidity.
The PCB also includes additional features/slots for:
- s3231 i2c rtc clock module for keeping Real world time
- Capable of switching 16 hours light and 8 hours darkness 
- 0.96 Oled I2C SSD1306 with 4 buttons

## **How it works**
- **Power supply:**  
  It is powered by **12V barrel jack**, which breakes into smaller 5V to power arduino and sensors via a LM2596 buck.
The 12 V source is used to power the titillating/irrigation pump, whereas the 5V powers the dosing pump and draing pump.

- **Code:**
The example code provided works with  as an  simplified model for working with small scale hydroponics, with automated dosing according to TDS value, which can be caliberated in the code according to needs of user, along with alternating modes between manual and automatic nutrient dosing. While continiously
<table>
  <tr>
    <td align="center">
      <img src="https://github.com/GaneshKishore01/Smart-Hydroponics-PCB/blob/main/src/centre.png" width="400"/>
    </td>
    <td align="center">
      <img src="https://github.com/GaneshKishore01/Smart-Hydroponics-PCB/blob/main/src/centre.png" width="400"/>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img src="https://github.com/GaneshKishore01/Smart-Hydroponics-PCB/blob/main/src/centre.png" width="400"/>
    </td>
    <td align="center">
      <img src="https://github.com/GaneshKishore01/Smart-Hydroponics-PCB/blob/main/src/centre.png" width="400"/>
    </td>
  </tr>
</table>


---

## **Instructions**
1. Download `Hydroponic PCB.rar`.
2. **Extract** & **SOLDER** the components of PCB according to **BOM**`
3. **Upload** the code into `Arduino`.
5. Enjoy!

---
