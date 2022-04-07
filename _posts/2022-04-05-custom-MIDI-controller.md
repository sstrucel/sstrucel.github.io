---
layout: post
title: "Project Highlight: Custom MIDI Controller"
subtitle: Development of a custom Arduino Due based MIDI controller
thumbnail-img: /assets/img/drum.png
tags: [project, music, MIDI, C++]
---

**What:** This project is a custom MIDI/Keyboard controller that seamlessly lets the user use shortcut keys as well as MIDI messages to control the DAW of their choosing

**When:** Summer 2021

**Why:** When working with multiple devices for recording music I found my workflow was having to constantly change based on the DAW/device I was using. When using my computer I could easily use MIDI control offered by my MIDI keyboard. However, when creating music on the iPad the only option for DAW control was keyboard shortcuts or touch screen which interrupted my creative workflow. As a result I decided to build a custom device that would be able to have mappable buttons with feedback that could be plugged into the iPad or computer to provide a similar user experience.

**How:** The first thing that came to mind when finding a microcontroller to accomplish this was Arduino. I had worked with Arduino before on a previous project (Custom Wavetable Synth) and I hadn't been using that device so i could even borrow the Arduino Due controller that was powering it. The Arduino Due in particular is great for this project since it supports native USB control so that you don't need a serial translator to turn the output into MIDI/Keyboard message.

Once the controller was established the next task was to decide the device design and interface. I first started with a rudimentary protoype to ensure the idea was feasible and I implemented a handfull of buttons and rotary encoders. This prototype was fully functional but lacking in some features that I wanted (more buttons, visual feedback) so I started designing the final board. Using visio I drafted a plan to implement more buttons in an array configuration with a OLED screen for feedback on what the Arudino was doing with your input.

This involved setting up a custom library to help manage these functions in an object oriented manner. It is much easier to work with code when the functions can be encapsulated by more readable object oriented patterns (ex. screen.showIcon(ActionsEnum.Copy) vs the 20 lines it takes to make that happen). Once this library was created it became very easy to add new functionality to the device and every button is easily mappable to the desired keyboard/MIDI shortcut.

The only thing remaining on this project is to complete its housing. Currently I'm using a carboard box to situation the electronics in with the top being a sheet of plastic with the parts mounted on it. I toyed with the idea of buying a project box to house it but the dimension of the plastic sheet were custom so i would need a custom box which could get expensive. My current plan is to create my own wood box to house it this summer when the weather is nice for working with the wood outside.
