# Smart Glove for Sign Language Translation  
By [Suvom Karmakar](https://github.com/suvom027), [Sazzad Hossen], [Md. Tahman Hossain], [Azad Hossain Saykat], and [Sabiha Hossain Mim].

## [Click for Open Source of Project Details & Video](https://drive.google.com/drive/folders/1yu-9_WyVDk-NrpyH5Hro_kwHfU4WFT18?usp=sharing)

## Abstract  
Many people with hearing or speech impairments use sign language to communicate, but most of the general population does not understand it. This creates a communication barrier in daily life.  

Our project introduces a **smart glove** that helps bridge this gap by converting sign language gestures into **text and speech**. The glove is equipped with **flex sensors, an MPU6050 gyroscope, and contact sensors** to capture **finger movements, hand orientation, and touch patterns**. An **STM32 microcontroller** processes these signals and translates them into words using a **machine learning model**. This system ensures **fast and accurate** sign language recognition, making it a valuable tool for individuals relying on sign language.

## Introduction  
Sign language is essential for individuals with hearing or speech impairments. However, communication barriers arise as most people are not proficient in sign language. To address this, **smart gloves** have emerged as an innovative solution.  

Unlike traditional designs using low-power microcontrollers, our implementation utilizes an **STM32 microcontroller**, which offers **better real-time processing**. The glove integrates:  
- **Flex sensors** for finger bending detection  
- **MPU6050 accelerometer-gyroscope** for hand motion tracking  
- **Contact sensors** for distinguishing similar gestures  

By employing **machine learning** for gesture classification, we ensure a highly **accurate and efficient** system.

## Components  
- **Smart Glove:** Equipped with flex sensors, MPU6050, and contact sensors.  
- **STM32 Microcontroller:** Processes sensor data and transmits it to a computer.  
- **Computer & Python Algorithm:** Executes **machine learning-based** gesture classification.  

## Methodology  
The system converts hand gestures into text using a structured **sensor-data pipeline**:  
1. **Sensors Capture Gestures:** Flex sensors track finger movement, MPU6050 captures motion, and contact sensors detect finger contact.  
2. **STM32 Processing:** Converts sensor signals into structured digital data.  
3. **Data Transmission:** The processed data is sent to a **PC via a serial connection**.  
4. **Machine Learning Classification:** The **Python-based machine learning model** recognizes gestures and converts them into text/speech output.

## User Interface  
We designed an intuitive **PC interface** that:  
- **Displays recognized gestures in real-time**  
- **Allows debugging and visualization of sensor data**  
- **Provides a speech output for detected signs**  
## Hardware Design  

### Flex Sensor  
<p align="center">
  <img src="https://github.com/user-attachments/assets/808d4c90-d974-4515-9f5c-791676281a4e" width="400">
</p>
<p align="center"><b>Figure 1:</b> Flex Sensor</p>

- **Measures finger bending** using a **voltage divider circuit**.  
- The resistance increases from **10kΩ (straight)** to **27kΩ (fully bent)**.  

### MPU6050 Gyroscope  
<p align="center">
  <img src="https://github.com/user-attachments/assets/d2092f1c-6772-4eb1-a3f3-5ae3865361e3" width="400">
</p>
<p align="center"><b>Figure 2:</b> MPU6050 Gyroscope</p>

- Captures **hand orientation and motion**.  
- Communicates with STM32 via **I2C protocol**.  

### Contact Sensors  
- Helps differentiate **similar hand gestures** (e.g., "U" vs. "V").  

### Voltage Regulation  
- The STM32 operates at **3.3V**, ensuring compatibility with all sensors.  

<h1 align= "center">

**Hardware Implementation**
</h1>
<p align="center">
<img src="https://github.com/user-attachments/assets/c1a4a7ee-3fa4-43f0-bfc2-c602250caefe", width="620">
</p>

## Software Implementation  
### I2C Communication  
- Enables STM32 to communicate with the **MPU6050 sensor**.  

### Machine Learning Model  
- Uses **Support Vector Machines (SVM)** for gesture classification.  
- Achieves **98% accuracy** across 28 American Sign Language (ASL) signs.  

### Data Processing  
- **Real-time prediction** without requiring a button press.  
- **Noise filtering** improves accuracy.  

<h1 align="center">
    <strong>Results & Analysis</strong>
</h1>
<p>Our <strong>smart glove</strong> successfully recognizes <strong>28 ASL signs</strong>, achieving:</p>
<ul>
    <li><strong>98% accuracy</strong> for trained users.</li>
    <li><strong>Satisfactory results</strong> for non-trained users.</li>
    <li><strong>Smooth real-time recognition</strong> (prediction speed: ~3 times per second).</li>
</ul>


## American Sign Language (ASL)

To ensure accuracy, we compare the **reference ASL signs** with the **hardware-detected ASL signs**. Below are the comparisons:

<p align="center">
<strong>Reference ASL</strong><br>
<img src="https://github.com/user-attachments/assets/d518ab70-33e3-400e-8761-d8e78f819548" width="300">
</p>


<p align="center">
    <strong>Hardware-Detected ASL "A"</strong><br>
    <img src="https://github.com/user-attachments/assets/0441eb5f-b764-42ea-9125-8c29abb8cc03" width="100">
    <strong>Hardware-Detected ASL "B"</strong><br>
    <img src="https://github.com/user-attachments/assets/9a2a77b8-9225-4be9-91e5-8eed38ac35b5" width="100">
    <strong>Hardware-Detected ASL "L"</strong><br>
    <img src="https://github.com/user-attachments/assets/56ca4392-c7bf-44d3-8111-316ea302dedd" width="100">
</p>
## Applications  
- **Assistive technology for speech-impaired individuals**  
- **Gesture-based control systems**  
- **Interactive computing and gaming**  

## Conclusion  
The **Smart Glove for Sign Language Translation** effectively converts **hand gestures into text and speech**, offering **high accuracy and real-time performance**. Future improvements will focus on:  
- **Wireless communication** (Bluetooth integration).  
- **Enhanced contact sensor accuracy**.  
- **Optimizing portability and comfort**.
