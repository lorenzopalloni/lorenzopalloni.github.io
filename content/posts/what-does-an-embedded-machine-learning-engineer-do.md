---
title: "What Does an Embedded Machine Learning Engineer Do?"
date: 2024-03-06T07:28:41+01:00
draft: true
tags: ["embedded-systems", "machine-learning", "engineering"]
---

## How I Earned "Embedded" in My Title
Two years ago, I joined the company where I currently work as a Machine Learning Engineer. My main responsibility was to develop an Instance Segmentation model (Computer Vision) for a real-time application using Python. After a year, the project was halted due to a lack of funding from the external automotive company that was sponsoring it.

Around the same time, the only Embedded Firmware Engineer in the company, whom I'll refer to as `Foo`, decided to leave. Our CTO, aware of my interest in low-level programming, approached me with an unexpected opportunity. He asked me if I could take on `Foo`'s responsibilities temporarily until a new Embedded Firmware Engineer could be hired.

`Foo` was maintaing the firmware for a custom piece of hardware made by my company. At that time, I dind't even know what an Arduino actually was.

I accepted the challenge because I knew I would enjoyed a period coding with a low-level programming language such as C. So, I started taking on `Foo`'s work while learning the basics of Embedded Systems, though I wasn't very confident in my choice at first.

The more time I spent learning, the more I realized how difficult this field was to master.
However, my passion grew alongside the difficulties I faced.
I started to develop a curiosity about current, voltage, resistance, and Electronics in general. I couldn't believe that behind those tiny, little pieces, there was such a gigantic world.

In the meantime, the hiring process for a new Embedded Firmware Engineer was taking longer than usual, likely due to the summer period when the pace of work in Italy tends to slow down.

When `Foo` ended his notice period, I didn't expect to become so captivated by this field.

The firmware was barely funtional - and trust me, getting it to work is no easy task, so kudos for the previous engineers. I had to rewrite the entire firmware multiple times to meet the project requirements.

After a couple of months delving into the subject, I realised I was developing a new purpose: I wanted to bridge the gap between Embedded Systems and Machine Learning. I knew from the start it would take me an enormous amount of time to learn the basics of Embedded Systems. I had experience in Computer Programming, but I had no clue of how current works. I am a big fan of hard challenges, so I step into this career shift, asking my line manager to stop seeking a new Embedded Firmware Engineer, confident that I would replace the old `Foo` pretty soon.
One year has passed, and now I am fully recognized as an Embedded Machine Learning Engineer.
I got a new title and a +22% raise of my previous salary, that's huge! Not only for the money, but especially for the recognition of the quality of my work. Now I feel I can indipendently work as an Embedded Firmware Engineer as well as an ML Engineer.

The path through here hasn't been easy at all. I spent the majority of my time learning and solving work issues. I was lucky to be able to work on a custom PCB featuring an nRF52840 (ARM Cortex-M4) with several sensors (ADC, IMU, PPG, Fuel Gauge), where the firmware was barely working. I had to adjust the whole firmware infrastructure to make the board streaming at specific frequencies each sensor's values through BLE (Bluetooth Low Energy) technology.

I started to write this post while I was trying to outline the job description of my new role. Online I couldn't find much information about which responsibilities an Embedded Machine Learning Engineer actually has, so I thought it could be helpful for someone other than me to start writing something on my own.

The job description is technical and somewhat specific to my current role, within the company I am working for. However, I believe it can serve as a starting point.


I read the book "Making Embedded Systems" by Elicia White, I leverage a lot ChatGPT as a personal tutor, asking questions after questions about what I didn't know.
I watched a lot of YouTube courses, from Miro Samek's 

It is June 2024, and there is no unique definition of what an Embedded Machine Learning Engineer does. The field is still evolving, and the roles and responsibilities of an Embedded Machine Learning Engineer can vary widely depending on the organization and the specific project.
I had to write my own job description for my current role, and I thought it would be helpful to share it with others who are interested in this field.

The job description is technical and somewhat specific to my current role, within the company I am working for. However, I believe it can serve as a starting point.

```
Job Title: Embedded Machine Learning Engineer
 
Role Overview:
As an Embedded Machine Learning Engineer, you will collaborate with a highly interdisciplinary team to deliver end-to-end (software and hardware) application-use cases. Your work will involve developing, deploying, and maintaining firmware as well as Machine Learning pipelines, ensuring they run efficiently on our hardware platforms. This role is critical in creating intelligent, efficient, and reliable embedded systems that power our innovative products.
 
Responsibilities:
- Collaborate with a highly interdisciplinary team to deliver end-to-end (software and hardware) application-use cases.
- Develop, deploy, and maintain firmware and ML pipelines, ensuring they are robust, reproducible, and efficient.
- Analyze, profile, and benchmark firmware and ML models and pipelines to optimise for latency, memory, and power.
- Ensure accurate signal acquisition and data streaming at designated frequencies from various sensors like ADC (e.g., EEG, GSR, etc.), IMU, PPG.
- Contribute to the creation of IP (patents, know-how) and ensure the highest coding standards, documentation, and efficiency in product development.
- Stay up-to-date with the latest advancements in machine learning and embedded systems technologies and tools.
 
Skills and Qualifications:
 
Education:
- Master’s degree in Machine Learning, Data Science, Statistics, Computer Science, Electrical Engineering, or a related field. PhD is a plus.
 
Experience:
- Proven experience developing and deploying embedded or TinyML AI applications.
- At least 3+ years of hands-on experience delivering AI solutions.
- At least 1+ year of hands-on experience writing firmware for Embedded Systems.
- Experience with time-series data and sensor data.
- Familiarity with hardware AI accelerators architectures.
 
Technical Skills:
- Proficiency in Python (NumPy, Scikit-learn, TensorFlow, PyTorch) and strong programming skills in C/C++.
- Experience with Machine Learning model optimization techniques (e.g., quantization, pruning).
- Knowledge of neural network inference engines like ONNX Runtime, TensorRT, TFLite for Microcontrollers.
- Solid experience in software design, implementation, debugging, and profiling.
- Practical experience with Linux, version control systems (e.g., Git), build systems (Make, CMake).
- Experience with edge AI (e.g., Jetson Nano, Raspberry Pi) and IoT devices (e.g., nRF52840, ESP32).
- Familiarity with embedded operating systems like FreeRTOS and Zephyr.
- Knowledge of hardware interfaces and communication protocols like UART, SPI, I2C, etc.
- Knowledge of wireless communication technologies like BLE.
- Proficiency with electronics lab tools (e.g., oscilloscope, soldering iron, bench power supply) for essential hardware tweaks.
 
Soft Skills:
- Problem-solving and goal-oriented attitude.
- Excellent analytical skills and a good mathematical background.
- Strong verbal and written communication skills.
- Ability to work in a dynamic and interdisciplinary team environment.
```

Too many big words for only one title, I know.
Engineer is the easy one.
What are Embedded Systems? What is Machine Learning?

An Embedded Machine Learning Engineer is in charge to bridge the gap between Embedded Systems and Machine Learning.

Embedded Systems is the field that regard tiny devices made for a specific purpose.
Machine Learning is a branch of Artificial Intell

- I transitioned from ML to Embedded Systems, since all the Embedded Software Engineers left the company and I was the guy with most interest in low-level programming I took the chance to embark in this new unseen field.
- I learnt how the current works through self-learning, with books such as Make: Electronics, Make: More Electronics, I spent more than 1.5k euro in a home lab that I'm really proud of. I learnt the basis of RTOS with the Miro Samek's course, I enjoyed Making Embedded Systems by Elicia White, 

To understand what an Embedded Machine Learning Engineer does, we need to break down the title into its components: "Embedded", "Machine Learning", and "Engineer".

### Embedded
Embedded systems are computing systems that are designed to perform a specific task. They are often found in consumer electronics, automotive systems, and industrial machines. They are different from general-purpose computers in that they are optimized for a specific task and are often resource-constrained.

### Machine Learning
Machine learning is a subfield of artificial intelligence that focuses on the development of algorithms that can learn from and make predictions or decisions based on data. Machine learning algorithms can be used to recognize patterns in data, make predictions, and optimize processes.

### Engineer
An engineer is a person who designs, builds, or maintains systems or products. Engineers use scientific and mathematical principles to solve problems and create new technologies.


### Job description

Job Title: Embedded Machine Learning Engineer

Role Overview:
As an Embedded Machine Learning Engineer, you will collaborate with a highly interdisciplinary team to deliver end-to-end (software and hardware) application-use cases. Your work will involve developing, deploying, and maintaining firmware as well as Machine Learning pipelines, ensuring they run efficiently on our hardware platforms. This role is critical in creating intelligent, efficient, and reliable embedded systems that power our innovative products.

Responsibilities:
- Collaborate with a highly interdisciplinary team to deliver end-to-end (software and hardware) application-use cases.
- Develop, deploy, and maintain firmware and ML pipelines, ensuring they are robust, reproducible, and efficient.
- Analyze, profile, and benchmark firmware and ML models and pipelines to optimise for latency, memory, and power.
- Ensure accurate signal acquisition and data streaming at designated frequencies from various sensors like ADC (e.g., EEG, GSR, etc.), IMU, PPG.
- Contribute to the creation of IP (patents, know-how) and ensure the highest coding standards, documentation, and efficiency in product development.
- Stay up-to-date with the latest advancements in machine learning and embedded systems technologies and tools.

Skills and Qualifications:

Education:
- Master’s degree in Machine Learning, Data Science, Statistics, Computer Science, Electrical Engineering, or a related field. PhD is a plus.

Experience:
- Proven experience developing and deploying embedded or TinyML AI applications.
- At least 3+ years of hands-on experience delivering AI solutions.
- At least 1+ year of hands-on experience writing firmware for Embedded Systems.
- Experience with time-series data and sensor data.
- Familiarity with hardware AI accelerators architectures.

Technical Skills:
- Proficiency in Python (NumPy, Scikit-learn, TensorFlow, PyTorch) and strong programming skills in C/C++.
- Experience with Machine Learning model optimization techniques (e.g., quantization, pruning).
- Knowledge of neural network inference engines like ONNX Runtime, TensorRT, TFLite for Microcontrollers.
- Solid experience in software design, implementation, debugging, and profiling.
- Practical experience with Linux, version control systems (e.g., Git), build systems (Make, CMake).
- Experience with edge AI (e.g., Jetson Nano, Raspberry Pi) and IoT devices (e.g., nRF52840, ESP32).
- Familiarity with embedded operating systems like FreeRTOS and Zephyr.
- Knowledge of hardware interfaces and communication protocols like UART, SPI, I2C, etc.
- Knowledge of wireless communication technologies like BLE.
- Proficiency with electronics lab tools (e.g., oscilloscope, soldering iron, bench power supply) for essential hardware tweaks.

Soft Skills:
- Problem-solving and goal-oriented attitude.
- Excellent analytical skills and a good mathematical background.
- Strong verbal and written communication skills.
- Ability to work in a dynamic and interdisciplinary team environment.

