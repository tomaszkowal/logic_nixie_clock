This project is based on few core ideas:
1. No programmable ICs
2. ICs must be from 4000 series logic
3. Other semiconductors allowed are discrete diodes and transistors
4. Display time using nixie tubes
5. Use mains frequency for base clock source
6. Have a backup voltage supply which should last about a day
7. Have a backup 32768 Hz crystall oscillator with automatic clock switchover in event of mains power loss
8. Supply provided by two back to back transformers
9. Support for 50 and 60 Hz mains
10. Support for 12hr and 24hr standards
11. AM/PM indication via separate neon bulbs or PM indication using decimal point of tens of hours tube
12. 1 Hz, 50% duty cycle blinking colons or constantly lit colons, support for separate neons or decimal points in tubes
13. Use SOIC, SOT-23 and 0805 packages whenever possible - SMD, but easy to solder
14. Hacky technicques of mounting components* permitted
*for example, soldering a capacitor with 1-2 mm standoff to avoid contact with another THT pad

Revision 1.0 has been produced, unfortunately before I started using git so the exact files are lost, but it wasn't a good version anyway so expect rev 2.0 soon(tm). 
Revision 1.0 proved the logic works well, the only major issue is that I underestimated losses in chosen transformers and need to rewire the secondary transformer to full bridge configuration. 
