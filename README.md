# Intro to Node-Red
Node RED is a wonderful tool which makes prototyping a lot faster and easier!  Node Red is very easy to get started with and is a great tool for beginners who want to write and understand programming flow. 

It provides lot of tools and plugins which supports almost everything related to programming. It can be used for APIs, DataBase, IOTIntro to IBM's Node-RED, WebSockets, Emails, Scripting, Image Processing, Cloud computing, edge computing, creating websites and lot more one can think of doing it based on NodeJS. In this workshop we will go over the basics of Node Red to help you all get started with the prototyping process! 

## Workshop Topics Outline :
1. Creating a IBM Cloud Account 
2. IBM Cloud Overview 
	- [How to Create an IBM Cloud Account](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Docs/Getting%20Started%20with%20IBM%20Cloud%20and%20NodeRED.pdf)
	- [How to Get Access to Node-Red and other Services on IBM Cloud](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Docs/Getting%20started%20with%20IBM%20Services.pdf)
3. Node-RED Overview  
 	- Concept of flows and nodes 
 	- Input & Outputs 
 	- Debug & ingect nodes 
4. [More Node Red Resources](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Docs/NodeRedResources.pdf)


Presenter: [Pooja Mistry](https://github.com/pmmistry)

# Step 1 : Sign up for IBM CLOUD [HERE](https://ibm.biz/Bdzbbw) 

## Node-RED flows in this repository: 
### 1. This flow describes how to create the basic Hello World in a few steps.
1. Drag an Inject node from the palette
2. Drag a Debug node from the palette and wire the two nodes together
3. Double click on the Inject node and change it to inject an A-Z String "Hello World"
4. Press the Red Deploy button in the top Right corner. Press the blue Inject. The Hello World string will appear in the Debug area.
![Hello World](/Screenshots/HelloWorld-Inject-annotated.png?raw=true "Hello World")

**Import flow from here :** [HelloWorld](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloWorld.flow)

### 2. This flow describes how to use the function node to perform a function
1. Drag the function node from the palette and connect it between the inject node and debug node
2. Double click on the function node and add code in the function input, e.g: 
```
var newString = msg.payload.replace("World","Everyone , I hope you enjoy Node Red ");

return {payload : newString};
```
This example replaces World with `Everyone, I hope you enjoy Node Red  ` 

3. Press red Deploy on the right corner and see : 
![Hello Replace](/Screenshots/HelloWorldReplace.png?raw=true "Hello World Replace")

**Import flow from here :** [HelloWorldReplace](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloReplace.flow)


### 3. This flow describes how to use the language translation node:
1. Drag a Language Translation node from the palette.
2. Double click on the Language Translation node and select German (Language Translation Set up can be found in : [How to request Access to Services](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Docs/Getting%20started%20with%20IBM%20Services.pdf) )
3. Connect the Language Translation node in between the Inject node and the debug node 
4. Press the Red Deploy button in the top Right corner. Press the blue Inject. The string from the inject node will appear in the Debug area along with the translated text.
![Language Translation](/Screenshots/IchbineinBerliner-Translate-annotated.png?raw=true "Ich bin ein Berliner")

**Import flow from here :** [HelloWorldGerman](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/helloWorldGerman.flow)


### 4 . Hello World in Spanish - Convert Text to Speech 


![](https://paper-attachments.dropbox.com/s_47B19C1398BE4DA15B3A75EC8B94D22D2E4AA20C6FFB4054F0EB3B366D945110_1569262059697_Screen+Shot+2019-09-23+at+1.55.20+PM.png)

**Import flow from here :**  [HelloWorldSpeech](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/languagespeach.flow)

### 5. This flow describes how to use the Weather Insights , Language translator , and Speech to Text

This flow speaks the Berlin weather forecast in German  
	- Call the Weather Insights for the forecast in Berlin.
	- Builds a sentence
	- Call language translation to convert to German
	- Call Text to Speech to generate a WAV file
	- Plays the weather forecast in a German voice
![Weather Forecast](/Screenshots/WeatherForecastinGerman.png?raw=true "Speak the Berlin weather forecast in German")

 **Import flow from here :** [Weather](https://github.com/pmmistry/Intro-to-Node-RED/tree/master/Flows)

### 6. Webpage 
![](https://paper-attachments.dropbox.com/s_47B19C1398BE4DA15B3A75EC8B94D22D2E4AA20C6FFB4054F0EB3B366D945110_1569262682714_Screen+Shot+2019-09-23+at+2.17.45+PM.png)


This is a simple webpage 

Template Code : 
```
    <html>
        <head>
            <title>Hello World</title>
        </head>
        <body>
            <div><h1>This is a simple Webpage in Node-RED</h1></div>
            <div id="id_hello">
               <span>Hello</span>
               &nbsp;
               <span id="id_nameout"></span>
           </div>
            <form id="id_form">
                <div>
                    <span>
                        <h2>What is your name:</h2> 
                    </span>
                    <span>
                        <input type="text" name="name"        
                                         id="id_name"/>
                    </span>
                </div>
                <div>
                    <input type="submit" value="Enter"
                                          id="id_enter"/>
                </div>
            </form>  
            <script
               src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js">
         </script>
            <script type="text/javascript">
                $(document).ready(function(){
                    setupPage();
                });
                function setupPage(){
                    $('#id_hello').hide();
                    $('#id_form').submit(onSubmitClicked);
                    enterbutton();
                }
                function onSubmitClicked(event){
                    $('#id_nameout').text($('#id_name').val());
                    $('#id_hello').show();
                    $('#id_form').hide();
                    event.preventDefault();
                }
                function enterbutton(){
                    $(function() {
                        $("form input").keypress(function (e) {
                        if ((e.which && e.which == 13) || (e.keyCode && e.keyCode == 13)) {
                            $('#id_enter').click();
                            return false;
                        } else {
                            return true;
                        }
                    });
                });
            }
            </script> 
            <style> body {background-color: pink;}</style>
        </body>
    </html>
```

**Import flow from here :** [Basic Webpage](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/webpage.flow)


### 7. This flow describes how to build a chat service in a browser 
1. Drag the http node and create a Get Request 
```
Set Method to GET 
Set URL to /chat 
```
2. Drag the template node and insert chat source code. Connect with Get Request
souce code can be found at  [Chat Service Source Code](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/chatSourceCode.html)

3. Drag http response node and connect with template node 

4. Drag Websocket node to listen to http request node
5. Drag Funtion node and connect to websocket node 
```
delete msg._session;
return msg;
```
6. Drag websocket out node and listen on /ws/chat 

![ChatService](/Screenshots/Chat.png?raw=true "Chat Service")
![ChatService2](/Screenshots/ChatService.png?raw=true "Chat Service on the Browser")
**Import flow from here :** [ChatService](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/chatService.flow)


### 8. Simple Dashboard
This flow describes how to build a UI with the use of `node-red-dashboard` nodes 
We will need to install `node-red-dashboard` from manage pallet 
![](https://paper-attachments.dropbox.com/s_49EBF2EB36746BBC00471930A737A626223590B94A1CAFB75A0CD643C5F6FAAB_1569263698690_Screen+Shot+2019-09-23+at+2.23.21+PM.png)

**Import flow from here :** [Dashboard](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/dashboard.flow)


### 9. Sentiment Dashboard
This flow describes how we can measure the sentiment of incoming text 
![](https://paper-attachments.dropbox.com/s_49EBF2EB36746BBC00471930A737A626223590B94A1CAFB75A0CD643C5F6FAAB_1569263733561_Screen+Shot+2019-09-23+at+2.33.39+PM.png)

**Import flow from here :** [Sentiment Dashboard](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/sentimentdashboard.flow)


### 10. Twitter Input 
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

**Import flow from here :** [Twitter Example](https://github.com/pmmistry/Intro-to-Node-RED/blob/master/Flows/twitter.flow)
