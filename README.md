# Lab8 - "Synth Time" (Keypad Interrupts/TOC Speaker)

## 1. Introduction

The purpose of this lab is to explore the design of firmware using external interrupts to drive a keypad. The Piezo speaker will be driven by a TOC Timer. To test the firmware a "Synth" Keyboard application will be created with recording and playback capability.

## 2. Prerequisites

- A completed development board.
- Working Piezo speaker.

## 3. Activities


### 3.1 Create Project

1. Clone this project into your CubeIDE workspace directory with GitHub Desktop, WSL Git, or Windows Git.
2. In CubeIDE copy the Lab7 Project in the ProjectExplorer tab by copy-and-pasting using the same project name as the cloned directory.
3. Modify the rubric file adding your name and section number.
4. Make an initial commit.
5. Start working.
6. As you modify previous driver files be sure to updated the filed comment blocks.

### 3.2 Modify piezo(.c/.h) API 

- Modify your tone generation API to utilize Timer TOC functions to produce the square wave. 
	- No Interrupts should be used to generate the correct frequency square wave

- Add your to your API to add methods allow for your to 
	- Change the frequency
	- Turn the Speaker On
	- Turn the Speaker Off

	
### 3.3 Modify your keypad API to make it interrupt driven

- Convert your keypad API to make it interrupt driven with external interrupts.
	- Algorithm #2 as discussed in class must be used for the first stage so all keys can be watched at once.
	- Note: the isrs will likely be application specifice and not placed in the API.
	
### 3.4 Create synth player in main.c

1. Begin with a welcome screen
2. Map music notes to 1-9,A-D keys in a method you choose.
	- Print "Playing" to the first line
	- Print the note pitch and type on the second line
	- Play notes while in this PLAY Mode
3. Recording: (*Key)
	- Start a millisecond counter if the * Key is pressed.
	- Print "Recording" to the first line
	- Print the note index and note pitch and type on the second line
	- Notes begin on a down press and stop on the release.
	- Note these times in a sufficiently large song array.
	- Stop recording when the * Key is pressed again. 
4. Playback: (#Key)
	- Play the currently stored song back.
	- Print "Playback" to the first line
	- Print the note index and note pitch and type on the second line

## 4. Deliverables

- Demonstrate your working project to your instructor or lab assistant at beginning of Lab Week11.
- Commit **only** your "inc" and "src" directories
	- You may add any extra files to you *.gitignore* file to prevent future inclusion
- Use git to back up your work and track commits.
- Your final submission should be on the main branch
	- Clearly label the commit as "Lab8 Submission"
- Be sure to update all documentation.
