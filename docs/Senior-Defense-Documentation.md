# Modular Kontakt Audio Granulizer

April 19, 2023  
Carter Hinkle  
Computer Science  
Advised by Dr. Lin  


## Statement of Purpose (with the Problem Statement)
In the world of audio production, Kontakt is the industry standard sampler VST that allows you to play instruments (such as violin, cello, etc) digitally. Not only can the user play these instruments, but Kontakt has developed a language in which you can develop your own digital libraries. While most libraries focus on achieving realism and representing the instrument as well as possible, some companies push the boundaries and allow you to manipulate the sound creatively. An example of this is Noire by Galaxy Instruments. This is piano library is supported by many because of it's granular system named "particles". The problem is that many people want to use this engine with their own samples or others, but cannot.  
  
My Kontakt library implements an engine similar to Noire's, but is implemented using User Zones instead of Static Zones. This ultimately gives the user the capability to add, remove, and replace samples as they wish. All the user needs to do is create the sound they want, tune it to the proper key, and add the file to the Samples folder. They can then use the rest of the features I've implemented to extend the functionality of Noire's engine.  

## Research & Background
My research consisted mainly of contacting professionals in Discord servers and getting their opinions on my implementation. I have been developing Kontakt libraries before I began this project, and before that had some experience in C++ VST programming, so not much research was necesary.

## Project Language(s), Software, and Hardware
Project language: KSP (Kontakt Script Processor)  
Software: Kontakt 6 Standalone, Kontakt 6 VST3, Ableton Live  
Hardware: Windows 10 PC, 32gb ram, Ryzen 2700 processor.  

## Project Requirements
[View Project Requirements](Senior_Project_Requirements.md)

## Project Implementation Description & Explanation
The design of the software is this: A main page which allows sample randimization and simple controls, a randomize page which allows you to specify randomization parameters, an fx page which allows the user to add fx as they wish, and a granular tab which allows the user to granulate the audio.  

In scope: sample randomization, granulizer  

Out of scope: Preset system, functional fx  

## Test Plan and Results
[View Test Plan](test_plan.md)

## Challenges Overcome
The save state and load state features were by far the hardest to implement. Spending weeks on this feature, I finally figured it out and learned a lot about state saving in the process.

## Future Enhancements
Create an easy UI for users to drag and drop their own samples  
Add more source content (currently 10 unique sounds)


## Defense Presentation Slides
[View Slides](https://docs.google.com/presentation/d/1cC_gkVYQiNpLZxWM08bVBli_dusfsFnf4SXxsV1A7OM/edit?usp=sharing)



