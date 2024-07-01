---
title: "How I Earned Embedded in My Job Title"
date: 2024-07-01T16:58:35+02:00
draft: true
tags: ["embedded-systems", "machine-learning", "engineering"]
---

Two years ago, on the 4th of July 2022, I joined an R&D company based in Parma as a Machine Learning Engineer. At that time, my main responsibility was to develop an Instance Segmentation model (Computer Vision) for a real-time application using Python. After working on it for about a year, the project was halted due to a lack of funding from the external automotive company that was sponsoring it.

Around the same time, the only Embedded Firmware Engineer in the company, whom I'll refer to as *Foo*, decided to leave. Our CTO, aware of my interest in low-level programming, approached me with an unexpected opportunity. He asked me if I could take on *Foo*'s responsibilities temporarily until a new Embedded Firmware Engineer could be hired.

*Foo* was maintaing the firmware for a custom embedded system to measure biosignals in a tiny, battery-powered stand-alone package. At that time, I didn't even know what an [Arduino Uno](https://en.wikipedia.org/wiki/Arduino_Uno) actually was.

I accepted the challenge because I knew I would enjoyed a period coding with a low-level programming language such as C. So, I started taking on *Foo*'s work while learning the basics of Embedded Systems, though I wasn't very confident in my choice at first.

The more time I spent learning, the more I realized how difficult this field was to master.
However, my passion grew alongside the difficulties I faced.
I started to develop a curiosity about current, voltage, resistance, and Electronics in general. I couldn't believe that behind those tiny, little pieces, there was such a gigantic world.

In the meantime, the hiring process for a new Embedded Firmware Engineer was taking longer than usual. This, was likely due to the summer period, when the pace of work in Italy tends to slow down.

When *Foo* ended his notice period, I didn't expect to become so captivated by this field.

I had to put my hands on a firmware that was barely funtional for the hardware available - and trust me, getting it to work is no easy task, so kudos for the previous engineers that were working on this. I had to rewrite most of the firmware's main logic, focusing on design patterns to handle asyncronous events to meet the project requirements.

After a couple of months delving into the subject, I realised I was developing a new purpose in life: I wanted to bridge the gap between Embedded Systems and Machine Learning. I knew from the start it would take me an enormous amount of time to learn the basics of Embedded Systems. I had experience in Computer Programming, but I had no clue of how current works. I am a big fan of hard challenges, so I step into this career shift, asking my line manager to stop seeking a new Embedded Firmware Engineer, confident that I would replace the old *Foo* pretty soon.
One year has passed, and now I am fully recognized as an **Embedded Machine Learning Engineer**.
I earned "Embedded" in my title and a +22% raise of my previous salary, from 31.5K to 38.5K of Annual Gross Salary, that's huge! Not only for the money, but especially for the recognition for the quality of my work. Now I feel I can indipendently work as an Embedded Firmware Engineer as well as an ML Engineer.

The path through here hasn't been easy at all. I spent the majority of my time learning and solving work issues. I was lucky to be able to work on a custom PCB featuring an nRF52840 (ARM Cortex-M4) with several sensors (ADC, IMU, PPG, Fuel Gauge), where the firmware was barely working. I had to adjust the whole firmware infrastructure to make the board streaming at specific frequencies each sensor's values through BLE (Bluetooth Low Energy) technology.

I know that so far I haven't had the chance to apply ML algorithms on tiny embedded devices at work, but I've started doing some stuff on my own following books such as "TinyML Cookbook" by Gian Marco Iodice and "TinyML Machine Learning with TensorFlow Lite on Arduino and Ultra-Low-Power Microcontrollers" by Pete Warden and Daniel Situnayake.
