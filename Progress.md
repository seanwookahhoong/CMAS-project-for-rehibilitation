# DISCLAIMER
This is my reflection when doing this project so it is going to have my thoughts on what I felt about the project.
I will be splitting the progress report by weeks, then I will further split between my reflections and the actual how to-dos for future reference or future interns. I will be marking the how to-dos with **``(Tutorial)``** so you don't have to read the whole document. FInally, very important dsiclaimer, I highly recomend you to learn much more stuff about the unity engine as this stuff is very bare bones and is meant to help you to start understanding. I recomend you to check out the other unity tutorials to understand scripting and other stuff more

# Week 0
## Reflections
I was briefed about the project and I learned that I am going to make games and improve on existing ones that my seniors have already made for my Final year project.
 I was also briefed of what things I will be using:
 * Unity 3D
 * Visual studio
 * MIDI Code(Music Generation)
  * Leap Motion Control(Input device)

For this week, I will do research and also meet with my seniors who have worked on the project before to make sure that I can get their vision for this project, which is necessary for its completion and excellence

### Senior meeting
I met my senior yesterday who worked on the project the last semester. He briefed me about the progress of the project and what I have to do. He told me that there were two games for the project. The first game was completed but the second was not. Thus, my FYP for this semester is to fix the problems of the second game.
These are the problems:
* Glitches
	* The ball would glitch out of the game when hands are in the air(Ball doesn't respawn during this) --> probably caused by the hands and when they suddenly appear it creates space thus getting more and more

* Ball       
	* Bigger
	* Add weight

* General
	* Make the game more engaging
	* Make scoreboard have a purpose
	* Add difficulty levels
	* Make ball easier to pick up
* Possible areas to explore
	* AR applications
	* AI integration
	
### Download things ``(Tutorial)``
### Step 1: Download relevant software
First, go to [this website](https://unity3d.com/get-unity/download/archive) and download this version(Unity 2018.4.18). Download unity hub and download the version of unity.

Then, to go the [leap motion SDK webiste](https://developer.leapmotion.com/sdk-leap-motion-controller/) and download for you relevant OS system. You will now be able to use the leap motion controller for your project.
You also need to go to [this website](https://developer.leapmotion.com/unity) and install the required unity packages needed to create games in unity

**You should put all of the leap motion controller stuff in one folder in your desktop for convenience purposes cause these files are very important**

### Step 2: Setting up software
After you have downloaded unity, you will need to get a license from unity, go to unity hub and sign in. Use this account
Username: ERunitymidicode
Password: Iwanttoquitthisproject295
After that, if the license is expired, you just renew it and say its a personal one.
After your done with that there is nothing to do for the week

# Week 1-2
## Reflections
I was tasked by my lecturer to do two things 
1.  Discuss with the other engineering rehabilitation people how to make a rehabilitation course with our products
2. To make a piano with 3-5 keys that play a note in Midi code in about two weeks, knowing my first ever task on this project. I went to research about how to make the piano

I have been busy with a project called TIP in the first week and thus I was able to work on the piano only in week two. Though I was able to discuss the project with the ER(engineering rehabilitation) student about what direction to have our rehabilitation course to go

### 1.Engineering rehabilitation meeting
We met during the first week and we were discussing how we could combine our ideas here are the slides we presented to our lecturers
he said that there need to be 1-2 research papers/ newspaper articles to back up our data. Also, the flowchart needs to be more detailed.
He also said to explain each of our projects more.


### 2. Piano making ``(Tutorial)``
Firstly, I watched this course called ["Learning C#"](https://www.linkedin.com/learning/learning-c-sharp-3/welcome?u=2122804) and learnt about the basics of C# and it is used to do scripting for making games
For a quicker tutorial, go to the [W3 schools C# tutorial](https://www.w3schools.com/cs/default.asp) to learn about the basics or C#


Then, used this tutorial called [roll a ball](https://learn.unity.com/project/roll-a-ball) where I learnt the basics of unity and how it works. Make sure you follow the tutorial that corresponds to the version of unity you are using

After that, I watched [this video](https://www.youtube.com/watch?v=bkE1YSSdOLU) as reference for making the piano in unity 
If you want a TLDR, The piano is bascially the keys of the piano are buttons and those button is attached to a script that plays a waveform file.
# Week 3-4
## Reflection
We went to improve our slides, we put one or two research papers and did slide for each of our products. Mr Kumar, our lecturer saw our slides again. He said that we need to ut the slides and condense the inportant parts into one or two slides. Also he said that we needed to have a visual representation for the activities that our persona was going to take, like a journey map. [This is the result](https://docs.google.com/presentation/d/1vsQg8oJ8cghKpDwymf43qRa_E8egsArUv6SBYQWkEuQ/edit?usp=sharing)
With our final slides ready, we just had to wait for the persenatation with the director of our school

### Midi Code``(Tutorial)``
Check out [this website](https://www.codeguru.com/columns/dotnet/making-music-with-midi-and-c.html) on how you should do midi code 
It can be very confusing and basically the format for your midi code should be:
```
using System;
using System.Collections;
using System.Collections.Generic;
using System.Runtime.InteropServices;
using System.Text;
using System.Threading.Tasks;
using UnityEngine;

public class Play_midi : MonoBehaviour
{
    // MCI INterface
    [DllImport("winmm.dll")]
    private static extern long mciSendString(string command,
       StringBuilder returnValue, int returnLength,
       IntPtr winHandle);

    // Midi API
    [DllImport("winmm.dll")]
    private static extern int midiOutGetNumDevs();

    [DllImport("winmm.dll")]
    private static extern int midiOutGetDevCaps(Int32 uDeviceID,
       ref MidiOutCaps lpMidiOutCaps, UInt32 cbMidiOutCaps);

    [DllImport("winmm.dll")]
    private static extern int midiOutOpen(ref int handle,
       int deviceID, MidiCallBack proc, int instance, int flags);

    [DllImport("winmm.dll")]
    private static extern int midiOutShortMsg(int handle,
       int message);

    [DllImport("winmm.dll")]
    private static extern int midiOutClose(int handle);

    private delegate void MidiCallBack(int handle, int msg,
       int instance, int param1, int param2);

**Enter the rest of your code here**

    [StructLayout(LayoutKind.Sequential)]
    public struct MidiOutCaps
    {
        public UInt16 wMid;
        public UInt16 wPid;
        public UInt32 vDriverVersion;

        [MarshalAs(UnmanagedType.ByValTStr,
           SizeConst = 32)]
        public String szPname;

        public UInt16 wTechnology;
        public UInt16 wVoices;
        public UInt16 wNotes;
        public UInt16 wChannelMask;
        public UInt32 dwSupport;
    }

}
```
Your going to need the P/Invoke definitions(top of the line rest of your code) and you need the MidiOutCaps class(if you don't know what a class is pls redo the tutorials I made. You can follow the website that I linked to earlier but its cucial to understand how MIDI works first to make sure that this project won;t be so heard 

do a dropdown menu --> change the size of ball and the height of the hoop
make astetics to make it more real
fix the eternal falling ball problem
optional: do set commands to move profuct?
 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzQwMjU1MTQ4LDIwNzMxOTQ0MywzMDY2ND
cyNTUsMTIxNjMyMjQzLDE4OTQ3Mzc1OCw3ODkzMDY3NjMsNzky
NDMwNjcxLDE0MTIzODk1NDQsMTY2NDc5NTgyNSwzNzcyNjc2Nj
QsMTY2NDc5NTgyNSwyOTM5NDYxMiwtMjAzMzEzMzM3MCw1Njg5
Njk5MDYsLTk3NDcwNzcyNCw2NjQ0MzUzMzgsLTE3ODI2MjkxOT
gsNDEyNDc3MDI4LDY1NzQ4NTE2MCwtMTI4MzA4OTc1NV19
-->