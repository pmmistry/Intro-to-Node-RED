# Intro to Node-Red
Hack-athons are all about building prototypes! Node RED is a wonderful tool which makes prototyping a lot faster and easier!  Node Red is very easy to get started with and is a great tool for beginners who want to write and understand programming flow. 

It provides lot of tools and plugins which supports almost everything related to programming. It can be used for APIs, DataBase, IOTIntro to IBM's Node-RED, WebSockets, Emails, Scripting, Image Processing, Cloud computing, edge computing, creating websites and lot more one can think of doing it based on NodeJS. In this workshop we will go over the basics of Node Red to help you all get started with the prototyping process! 

## Workshop Topics Outline :
1. Creating a IBM Cloud Account 
2. IBM Cloud Overview 
	- How to Create an IBM Cloud Account 
	- How to Get Access to Node-Red on IBM Cloud 
	- How to request Access to Services 
3. Node-RED Overview  
 	- Concept of flows and nodes 
 	- Input & Outputs 
 	- Debug & ingect nodes 
4. More Node Red Resources 


Presenter: [Pooja Mistry](https://github.com/pmmistry)


## Node-RED flows in this repository: 
*This flow describes how to create the basic Hello World in a few steps.*
1. Drag an Inject node from the palette
2. Drag a Debug node from the palette and wire the two nodes together
3. Double click on the Inject node and change it to inject an A-Z String "Hello World"
4. Press the Red Deploy button in the top Right corner. Press the blue Inject. The Hello World string will appear in the Debug area.
![Hello World](/Screenshots/HelloWorld-Inject-annotated.png?raw=true "Hello World")


*This flow describes how to use the language translation node:*
1. Drag a Language Translation node from the palette.
2. Double click on the Language Translation node and select German
3. Connect the Language Translation node in between the Inject node and the debug node 
4. Press the Red Deploy button in the top Right corner. Press the blue Inject. The string from the inject node will appear in the Debug area along with the translated text.
![Language Translation](/Screenshots/IchbineinBerliner-Translate-annotated.png?raw=true "Ich bin ein Berliner")



