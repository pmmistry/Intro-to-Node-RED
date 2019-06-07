# Intro to Node-Red
Hack-athons are all about building prototypes! Node RED is a wonderful tool which makes prototyping a lot faster and easier!  Node Red is very easy to get started with and is a great tool for beginners who want to write and understand programming flow. 

It provides lot of tools and plugins which supports almost everything related to programming. It can be used for APIs, DataBase, IOTIntro to IBM's Node-RED, WebSockets, Emails, Scripting, Image Processing, Cloud computing, edge computing, creating websites and lot more one can think of doing it based on NodeJS. In this workshop we will go over the basics of Node Red to help you all get started with the prototyping process! 

## Workshop Topics Outline :
1. Creating a IBM Cloud Account 
2. IBM Cloud Overview 
	- [How to Create an IBM Cloud Account](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloReplace.flow)
	- [How to Get Access to Node-Red on IBM Cloud](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloReplace.flow)
	- [How to request Access to Services](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloReplace.flow)
3. Node-RED Overview  
 	- Concept of flows and nodes 
 	- Input & Outputs 
 	- Debug & ingect nodes 
4. More Node Red Resources 


Presenter: [Pooja Mistry](https://github.com/pmmistry)


## Node-RED flows in this repository: 
**This flow describes how to create the basic Hello World in a few steps.**
1. Drag an Inject node from the palette
2. Drag a Debug node from the palette and wire the two nodes together
3. Double click on the Inject node and change it to inject an A-Z String "Hello World"
4. Press the Red Deploy button in the top Right corner. Press the blue Inject. The Hello World string will appear in the Debug area.
![Hello World](/Screenshots/HelloWorld-Inject-annotated.png?raw=true "Hello World")

flow can be found [HelloWorld](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloWorld.flow)


**This flow describes how to use the language translation node:**
1. Drag a Language Translation node from the palette.
2. Double click on the Language Translation node and select German (Language Translation Set up can be found in : [How to request Access to Services](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloReplace.flow) )
3. Connect the Language Translation node in between the Inject node and the debug node 
4. Press the Red Deploy button in the top Right corner. Press the blue Inject. The string from the inject node will appear in the Debug area along with the translated text.
![Language Translation](/Screenshots/IchbineinBerliner-Translate-annotated.png?raw=true "Ich bin ein Berliner")

flow can be found [HelloWorldGerman](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloWorldGerman.flow)


**This flow describes how to use the function node to perform a function**
1. Drag the function node from the palette and connect it between the inject node and debug node
2. Double click on the function node and add code in the function input, e.g: 
```
var newString = msg.payload.replace("World","Everyone , I hope you enjoy Node Red ");

return {payload : newString};
```
This example replaces World with `Everyone, I hope you enjoy Node Red  ` 

3. Press red Deploy on the right corner and see : 
![Hello Replace](/Screenshots/HelloWorldReplace.png?raw=true "Hello World Replace")

flow can be found in [HelloWorldReplace](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloReplace.flow)

**This flow describes how to use twitter as an input**
1. Drag the twitter input node from the palette and connect it with the debug message node 
2. Double click on the twitter node and set up twitter authentication 
	- Steps to set up Twitter 
	- Click on the little pencil button next to Twitter ID field 
	- Add Twitter ID 
	- Create your own application at ` developer.twitter.com/en/apps` 
	- Submit your API Keys and Access Tokens 
3. Once Twitter set up is complete you can receive tweets from hashtags, ids and any strings 
4. Press red Deploy button and see : 
![Twitter](/Screenshots/TwitterExample.png?raw=true "Twitter Example")

flow can be found in [Twitter Example](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/twitter.flow)


**This flow describes how to use the Weather Insights , Language translator , and Speech to Text**

This flow speaks the Berlin weather forecast in German  
	- Call the Weather Insights for the forecast in Berlin.
	- Builds a sentence
	- Call language translation to convert to German
	- Call Text to Speech to generate a WAV file
	- Plays the weather forecast in a German voice
![Weather Forecast](/Screenshots/WeatherForecastinGerman.png?raw=true "Speak the Berlin weather forecast in German")

flow can be found in [Weather](https://github.com/pmmistry/Intro-to-Node-RED/tree/master/Flows)

















