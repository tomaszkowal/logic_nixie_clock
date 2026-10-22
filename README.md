Do you want to build a nixie clock, but you are tired of code writing being associated with AI vibe coding? Or perhaps you never like to write code, just like me? Or you just want to do things differently and want to use some half a century old CMOS technology?
Then perhaps this clock project is just for you!

Key project ideas:
1. Is a clock
2. Uses nixie tubes as display, IN-12, ZM118x or other rectangular front view with same pinout
3. Uses 4000 series integrated circuits exclusively for all the counting and logic 
4. Uses mains voltage for both power and clocking. Two back to back transformers are used to provide low and high voltages isolated from mains.
5. Has supercapacitor backup for logic power and a 32 kHz quartz oscillator as a backup clock, with automatic switchover, providing best of two worlds (mains long term stability and availability of clock source and power even during blackout). The display remains off during the backup operation.
6. Physical implementation does use SMD components mostly, but limited to only easy to hand solder packages - SOIC and 0805 - to make it still solderable by people with little to no experience
7. PCB design incorporates unorthodox methods - namely, transformers and HV cap soldered on a standoff. This is necessary to keep everything on one PCB small, but will require some guideline - or even pictures (to be added later) - to understand how to properly assemble it

Project status (as of 22.10.2026): rev 1.0 was manufactured, few minor issues were spotted. Rev 1.1 is being manufactured right now. Once rev 1.1 passes electrical testing, a 3D printed case will be designed. Files for the case will be added to the project repository. 
After that, a short guide on soldering and assembling the clock will be created. A broader and less chaotic feature description will be provided too. 

Project was born thanks to NiceThingsGuy who provoked me to make my own take at a microcontrolerless clock. 
Project has been inspired by other logic clocks which have been described on various blogs, especially by http://www.mcamafia.de/nixie/ncp_en/ncp.htm . I have based the ways method of US clock variant (not tested) and 32 kHz clock source are implemented on mcamafias project. I have undoubtfully been inspired by more blogposts (like danyk.cz's several logic clocks) but can't name any other specifically for any specific part of my circuit, so credits go to all of you lovely people who share your designs and ideas online. 
I don't think I have seen the dual clock method and automatic switchover in any of the designs - they were all either mains or 32 kHz oscillator based. I personally think that even best trimmed and temperature compensated crystal cannot beat EU grid frequency stability in the long term, but I also absolutely hate having to set every mains clocked clock after even brief power disruptions. Hence I implemented a supercapacitor (two dual supercaps in series, in fact) to keep just the logic part powered for a while and a local clock source in form of a classic 32 kHz crystal oscillator to keep the clock running. 
Due to startup period of a crystal oscillator it is kept running at all times - but the D flip flop doing the last /2 division is kept in steady state by presence of mains voltage.
Precision of the 32 kHz oscillator is worse than mains frequency on the long run, and the switchover is not perfect, introducing up to a second of error, but for a home clock it is generally fine - definitely better than having the clock reset to 00:00:00. Rev 1.0 tests show 24+ hours of operation on the backup supply.

The controls are fairly simple: three buttons allow to add seconds, minutes and hours (1 click = increment the counter by 1), a button to reset the clock to 00:00:00, and a button which halts the mains clock source. This allows for a sub second clock setting - allowing you to sync the second increment moment be matched to other clock. 
Warnings:
1. The buttons are functional when the clock is running on backup
2. Due to way they are introduced into the counter system, the add second/minute/hour buttons are active press/release depending on state of the clock. The most intuitive way to use them is to do short presses


Licensing:
Look, I am new to the concept of open hardware licenses. None seems to describe what I consider to be a fair, permissive open source license which would still protect me from blatant abuse.
I therefore apply a simple ruleset written in simple words for using files within this repository:
1. Do not use provided files in direct, unmodified way for profit 
2. You are free to manufacture the PCBs from files provided, assemble them and use the resulting clock for your own use or gift them to other people
3. You are free to manufacture multiple PCBs from files provided, and sell excess PCBs for price not exceeding cost of individual PCB in the production run
4. You are free to take the concept and make your own version of it on a ruleset of your choice, including closed and/or commercial use - I do not impose any inheritance of licensing rules on you (i.e. no ShareAlike), as long as your design has clearly had your input
5. When sharing this projects files, please do so by providing link to the github repository rather than sending individual files
6. I take no responsibility for any damages resulting from your use of this repository. I designed this clock in a way to make it as safe as possible and compliant with IPC norms regarding clearance and creepage (especially mains-to-the-rest-of-the-circuit), but in the end this is not a certified product, so you have to judge whether you trust me, a random person from the internet, to know what I am doing. I also do not take responsibility for your PCB quality, part choices, soldering and PCB cleaning skills.
The design involves lethal voltages and if you act irresponsibly around it, you might get hurt - or worse. I obviously do not take responsibility for that.
There are no exceptions to rule 6. If you find my design dangerous and/or not compliant with any norms, you are free (and encouraged to) open an issue on github. I will gladly take the criticism, but still - I take no responsibility.

So, you are free to do anything you want with this design EXCEPT for directly taking files from this repository as they are, manufacturing the clock or part(s) of it and selling it/them for profit. Put some effort in it if you want to make money.

Otherwise, I highly encourage you to play around and build your own clock(s) based on my ideas. 
Don't like the weird assembly? Make your own PCB! 
Don't like the tube type? Make your own PCB, or even a sandwich of two so you can swap tube types! 
Don't like SMD? All of parts used exist in THT variants! 
You can also go the other way around and use TSSOP ICs and smaller passive packages. You can change socket type. You can move this to 7400 series logic. You can change whatever you don't like about this project! 

This project is proudly 0% AI.
