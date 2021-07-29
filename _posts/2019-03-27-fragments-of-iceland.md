---
title: Virtual FPGA Lab - Part-1
excerpt: >-
  Iceland is a Nordic country between the North Atlantic and the Arctic Ocean.
  It has a population of 325,671 and an area of 103,000 km2 (40,000 sq mi),
  making it the most sparsely populated country in Europe.
date: '2019-03-27'
thumb_img_path: images/7.jpg
thumb_img_alt: Icelandic horses
content_img_path: images/7.jpg
content_img_alt: Icelandic horses
seo:
  title: Fragments of Iceland
  description: Iceland is a Nordic country between the North Atlantic and the Arctic Ocean.
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Fragments of Iceland
      keyName: property
    - name: 'og:description'
      value: >-
        Iceland is a Nordic country between the North Atlantic and the Arctic
        Ocean.
      keyName: property
    - name: 'og:image'
      value: images/7.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Fragments of Iceland
    - name: 'twitter:description'
      value: >-
        Iceland is a Nordic country between the North Atlantic and the Arctic
        Ocean.
    - name: 'twitter:image'
      value: images/7.jpg
      relativeUrl: true
layout: post
---

Photo by [Anders Jildén](https://unsplash.com/photos/uO4Au3LrCtk)

# Virtual FPGA Lab - Part-1
This is the first part of the three part blog series which covers the work done by me as part of my open source contribution to Google Summer of Code 2021 under FOSSi Foundation titled __Virtual FPGA Lab__.

## About the project
Field-Programmable Gate Array(FPGA) is a hardware circuit that a user can program to carry out logical operations. FPGAs are beneficial for prototyping application-specific integrated circuits (ASICs) or processors. The advantage of FPGA being energy-efficient, flexible to reprogram, support parallelism, decreased latency made them widely used in many applications. But the flexibility of FPGAs comes at the price of the difficulty of reprogramming the circuit. FPGA’s are a bit costly and difficult to learn for beginners. Also, students don’t have access to physical FPGA Lab classes in their curriculum amidst this pandemic situation. So there is a massive demand in having an alternative option of having an online simulator for FPGA curriculum development. 

This project __Virtual FPGA Lab__ aims to solve the problem by taking advantage of the VIZ Visualization feature in the Makerchip platform and provide visualizations of basic peripherals of an FPGA, thereby mimicking the physical lab experience.

Makerchip is a free web-based IDE as well as available as makerchip-app, a virtual desktop application for developing high-quality integrated circuits. You can code, compile, simulate, and debug Verilog designs, all from your browser. Your code, block diagrams, and waveforms are tightly integrated. Makerchip supports the emerging Transaction-Level Verilog standard. Transaction-Level Verilog, or TL-Verilog, represents a huge step forward, by eliminating the need for the legacy language features of Verilog and by introducing simpler syntax. At the same time, TL-Verilog adds powerful constructs for pipelines and transactions. More details about TL-Verilog: https://www.redwoodeda.com/tl-verilog

## Why TL-Verilog?
__Simple || Powerful || Flexible__
- Visual Debug
  - Waveform viewing have been our go-to debug tool for decades. Is there any way to visualize the simulations? Here you are!! With this cool feature, you can acheive that. Stay tuned, we will be discussing more about this.
- Easy Pipelining
- Organized Waveforms
  - No need of writing testbench to see the simulation. The IDE provides an inbuilt clock and assigns random values to signals whenever it is not assigned to any value.
- Organized Diagrams
  - Designs are represented in logic diagrams. Very easy to go through the design hierarchy, pipelining and stages.
- Less to code
  - Faster development
  - Fewer bugs 
  - Easier maintenance

My weeks of coding before the First Evaluation relies on adding the FPGA images on the VIZ canvas screen and support for visualizing FPGA LEDs, seven segment displays, LCD 16x2 display and VGA display.

## Power of Visual Debug
![logic_gates(./images/logic_gates.gif)]
Let us visualize the output of a simple digital logic gates. From the GIF above, we can see that the left portion is the coding part where you can see the logic of the gates and right portion is the Visual Debug(VIZ) part where you can see the visualization of each logic gates. We can move back and forth between cycles and see which cycle currently in the top right. Also, look at the waveform of the logic from the below image. Visualization looks visually pleasing to look at the output than waveforms.

__How Visual Debug is built?__
Visual Debug is a JavaScript canvas where we used [fabric.js](http://fabricjs.com/), which is a powerful and simple Javascript HTML5 canvas library framework. It provides us to use interactive object models on top of canvas element.

The real power of Visual Debug comes in play when the Verilog design is too complex and has huge lines of code. Here comes the idea of visualizing FPGA simulations, the __Virtual FPGA Lab__.


## What makes Virtual FPGA Lab special?
- Move back and forth between cycles so that we can visualize what's happening in each and every cycle.
- Faster to see the output for simple designs. No need to wait for Synthesis, Implementation and Bitstream Generation.
- Abstraction in writing the digital logic in TL-Verilog over standard HDL languages.
- Compatible code structure (works inside and outside of Makerchip)

In the second series of this blog, we will show the visualizations of FPGA LEDs, seven-segment display, LCD 16x2 display and VGA display.

# Virtual FPGA Lab - Part-2
This is the second part of the three part blog series which covers the work done by me as part of my open source contribution to Google Summer of Code 2021 under FOSSi Foundation titled __Virtual FPGA Lab__. In the second series of this blog, we will use the feature of Visual Debug and show the visualizations of FPGA LEDs, seven-segment display, LCD 16x2 display and VGA display.

### FPGA Boards demonstrated in Makerchip:
1. Basys 3 Artix-7 FPGA Trainer Board ([Product Link](https://store.digilentinc.com/basys-3-artix-7-fpga-beginner-board-recommended-for-introductory-users/)) 
3. EDGE Artix 7 FPGA Development Board ([Product Link](https://allaboutfpga.com/product/edge-artix-7-fpga-development-board/))
4. Zedboard Zynq-7000 ARM/FPGA SoC Development Board ([Product Link](https://www.avnet.com/wps/portal/us/products/avnet-boards/avnet-board-families/zedboard/))

Currently we demonstrate using only these three boards and we plan to add more boards in the future.
## LEDs
![Zedboard_LED](https://user-images.githubusercontent.com/15063738/124794052-3c88ea80-df6c-11eb-9da2-1e250868b6de.gif)
## Seven-segment display
![Basys3_7seg](https://user-images.githubusercontent.com/15063738/124794130-532f4180-df6c-11eb-8541-0f83f9ec47c6.gif)
## LCD 16x2 display

## VGA display