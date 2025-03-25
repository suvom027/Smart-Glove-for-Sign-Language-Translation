# Smart Glove for Sign Language Translation  
By Azad Hossain Saykat, Sazzad Hossen, [Suvom Karmakar](https://github.com/suvom027), Md. Tahman Hossain, and Sabiha Hossain Mim.

## [Click for Open Source of Project Details & Video](https://drive.google.com/drive/folders/1yu-9_WyVDk-NrpyH5Hro_kwHfU4WFT18?usp=sharing)

## Table of Contents
- [Abstract](#abstract)
- [Introduction](#introduction)
- [Components](#components)
- [Methodology](#methodology)
- [Hardware Design](#hardware-design)
- [Hardware Implementation](#hardware-implementation)
- [Software Implementation](#software-implementation)
- [Results & Analysis](#results-&-analysis)
- [American Sign Language (ASL)](#american-sign-language-(ASL))
-[Application](#application)
- [Conclusion](#conclusion)
   
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

 <h2>Components</h2>
    <ul>
        <li><strong>Smart Glove:</strong> Equipped with flex sensors, MPU6050, and contact sensors.</li>
        <li><strong>STM32 Microcontroller:</strong> Processes sensor data and transmits it to a computer.</li>
        <p align="center">
   <img src="https://github.com/user-attachments/assets/4b3adb00-7b06-465b-9c64-5ea7aa2b9514" alt="STM32 Microcontroller" width="300">
</p>
        <li><strong>Computer & Python Algorithm:</strong> Executes <strong>machine learning-based</strong> gesture classification.</li>
    </ul>

## Software Used
 <h2>Software:</h2>
    <ul>
        <li><strong>STM32CubeIDE</li>
        <li><strong>STM32 ST-Link</strong></li>
        <li><strong>PyCharm</strong></li>
    </ul>

## Methodology  
The system converts hand gestures into text using a structured **sensor-data pipeline**:  
1. **Sensors Capture Gestures:** Flex sensors track finger movement, MPU6050 captures motion, and contact sensors detect finger contact.  
2. **STM32 Processing:** Converts sensor signals into structured digital data.  
3. **Data Transmission:** The processed data is sent to a **PC via a serial connection**.  
4. **Machine Learning Classification:** The **Python-based machine learning model** recognizes gestures and converts them into text/speech output.


<p align="center">
    <img src="https://github.com/user-attachments/assets/5a535e1c-dfcd-46b4-8f35-41df85a9a1af" width="360">
</p>

<p align="center">
    <strong>Figure 1: Sensor-Data Pipeline Flowchart</strong>
</p>


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

<p align="center">
    <img src="https://github.com/user-attachments/assets/d9e72bc5-df8d-4d6c-b207-72dbd8cf0b41" width="300">
</p>

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
<img src="https://github.com/user-attachments/assets/d518ab70-33e3-400e-8761-d8e78f819548" width="400">
</p>


<p align="center">
    <img src="https://github.com/user-attachments/assets/0441eb5f-b764-42ea-9125-8c29abb8cc03" width="260">
    <img src="https://github.com/user-attachments/assets/9a2a77b8-9225-4be9-91e5-8eed38ac35b5" width="300">
    <img src="https://github.com/user-attachments/assets/56ca4392-c7bf-44d3-8111-316ea302dedd" width="250">
</p>

<p align="center">
    <strong>Fig: Hardware-Detected ASL "A", </strong>
    <strong>Hardware-Detected ASL "B", </strong>
    <strong>Hardware-Detected ASL "L"</strong>
</p>

 ## Application
- The **Smart Glove for Sign Language Translation** provides an innovative solution for speech-impaired individuals, enabling them to communicate more efficiently by translating hand gestures into text and speech. The system leverages an STM32 microcontroller and an MPU6050 gyroscope to track hand movements and orientation, ensuring precise real-time performance. Communication is facilitated through USART TTL, allowing seamless interaction and conversion of gestures.

- This project finds its primary application in assistive technology, acting as a bridge for individuals who rely on sign language. It also holds significant promise for gesture-based control systems, allowing it to be used as a controller for various devices by recognizing specific hand movements and translating them into commands. Moreover, the glove has the potential to transform interactive computing and gaming, enabling gesture-based inputs that create a more immersive and intuitive experience for users.

## Conclusion  
In conclusion, the **Smart Glove for Sign Language Translation** is a groundbreaking project that empowers speech-impaired individuals by converting hand gestures into text and speech, enabling smoother communication. The glove delivers accurate real-time performance by integrating an STM32 microcontroller, MPU6050 gyroscope, and USART TTL for communication. Beyond assisting individuals with sign language, this technology has broad applications in gesture-based control systems, interactive computing, and gaming, offering a more natural and immersive way to interact with devices. The project's potential to impact various fields makes it a significant innovation in both assistive technology and human-computer interaction.
