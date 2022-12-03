---
layout: post
title: "Project Highlight: Arduino Wavetable Synthesizer"
subtitle: Development of a Arduino Due based wavetable synthesizer
cover-img: /assets/img/soundwave.png
thumbnail-img: /assets/img/synthesizer.png
tags: [project, music, C#, C++]
---

This project is a wavetable synthesizer I built as part of my master of engineering degree at McMaster University

**When:** 2014

**Why:** As part of the masters degree program we got to select a project that posed an engineering challenge and I selected the challenge of creating a wavetable synthesizer with an Arduino Due.

**How:** The implementation of this synthesizer came in two parts. One was a C++ program made for playing sounds based on pre-generated wavetables and the second was a C# program that generated wavetables based on certain parameters.

The C++ program was made to be run on the Arudino Due and involved many low level operations to ensure the chipset could be pushed to its limit so it could keep up with the real-time nature of sound synthesis. The program had two threads, one that that read in the physical knobs and switches as parameters and one that was dedicating with figuring out the next value for the audio output. 

The parameter thread handled basic input and output functions to interact with the synthesizer physical knobs and turned them into parameters like filters and waveform selectors to modify the sound of the synthesizer. Additionally, this thread handled the MIDI input from the attached MIDI device so specific notes could be played by a MIDI controller. This parameter thread was loosely coupled to the audio thread so that delays in processing parameters would not cause missed values in the audio thread resulting in clicks and pops.

The audio thread dealt with the processing of the next sample and would read in wavetables from memory and apply parameters to get the correct sounds. Many low level optimizations were done on this thread to ensure the Arduino Due had the processing power to keep up with the next sample at 44kHz. In the end the audio thread could handle up to polyphony with up to 8 voice all controlled with various effects.

The C# program was a simple wavetable generator. It could generate wavetables based on equations or drawn lines. These data points were then exported to a format the Arudino Due could read so that they could be used as the base oscillators for the synthesizer.

Overall the project was an exciting introduction to what goes on behind a wavetable synthesis. It was rewarding to see such a simple piece of hardware be able to cleanly generate a variety of interesting sounds.   
