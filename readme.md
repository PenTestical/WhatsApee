[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com) [![forthebadge](https://forthebadge.com/images/badges/uses-js.svg)](https://forthebadge.com) [![forthebadge](https://forthebadge.com/images/badges/you-didnt-ask-for-this.svg)](https://forthebadge.com)
# WhatsApee [![Node version](https://img.shields.io/node/v/electron.svg?style=flat)](http://nodejs.org/download/) 
Whatsapee is a web based bot for Whatsapp.
This project is heavily inspired by [bruno222/whatsapp-web-bot](https://github.com/bruno222/whatsapp-web-bot)

A good substitute till WhatsApp releases their API  to the public.
However this code is not perfect for production it has a few bugs.

# How to use it?

 - Clone the git. 
 -  Install the latest npm and nodeJS for your platform. 
 - Then in repo folder run the following commands 
     ```npm install```   
   then run   
   ```npm start```
      
 - Signin using QR code and see the bot run your logic, stored in
   **logic.js**

# Bot Logic
 All code goes into the logic.js file
 WhatsApee has two function that you can use
 ```WhatsAppe.start( receiver callback)```  sets the callback for the message handler .It should take three arguments
 - message : body of message
 - chatElem : chat div element which is used as an identifier
 - title : chat title 
 
  ```WhatsAppe.send(chat Elem is like chat id , message to send goes here)```  sends message to the chosen element .It takes two arguments
 - chatElem : chat div element which is used as an identifier
 - message : body of message
 ## Example implementation
 ```
const path = require('path')
const WhatsApee = require(path.join(__dirname, 'WhatsApee.js'))
//WhatsAppe.start( receiver callback)
WhatsApee.start(receiver);

function receiver (message,chatElem,title) {
	  //message to lower case
	var lcMessage = message.toLowerCase();
      if (lcMessage.includes("hi bot")) {                  
                  var welcomeMessage = `Hi , hooman`;   
                  //WhatsApee.send(chat Elem is like chat id , message to send goes here)               
                  WhatsApee.send(chatElem,welcomeMessage);                  
      }  
      
}
```

# FAQ

#### So it's possible to create a Bot in Whatsapp Web?

Yes, it is.

#### Am I going to be banned?

Hum, so you already know that Whatsapp does not allow Bots, right?

Well, you're right: Whatsapp will ban you forever if they discovery you are running a Bot on long-term. For a small test: Don't worry, go forward.



**I can't guarantee that you are not getting banned in a long term using this Bot. I really don't think so, but I can't guarantee.**

#### Bullshit! I got banned using yowsup!

Hold on mate, there are kids here.

First, [yowsup](https://github.com/tgalal/yowsup) is a great python library! Simply awesome.

But their problem is: They connect to Whatsapp servers directly, without any middlware. So it is not so hard for whatsapp team to create ban-rules you if you are using yowsup.

I got banned many times in past, so I know, soon or later, you will get banned as well. Is just a matter of time.  You can see that I am probably right just looking [here](https://github.com/tgalal/yowsup/issues/1558), 
[here](https://github.com/tgalal/yowsup/issues/1979), 
[here](https://github.com/tgalal/yowsup/issues/1806) and
[here](https://github.com/tgalal/yowsup/issues/1686).

That's why I did this code. Using whatsapp web, it is almost impossible for whatsapp team to know that you are running a Bot.

#### But... What are the limitations?

A lot of limitations!

1. As you are handling DOM direcly, you can't process hundred of messages at once. Yowsup is much better at this subject.

2. You can't start a message with a unknown person. You can only answer them, mainly because you can't add a new fellow on the Contacts list on Whatsapp Web.

2. You have to install Whatsapp on your phone, connect it on Wifi and keep it charging all the time. So you have to have a cellphone exclusively for this Bot. You will need a computer with software running as well. But that's the main objective: In order to avoid being detect as a Bot, so you have to play this boring cat-and-rat game.

#### I think there're some bugs on your code.

Yes, there are.

1. Your friend can't send `@HELP` followed of any other message really fast. This Bot only reads the last message. It's a buggy (that can be fixed)

Feel free to fix and PR it. I will probably not touch in this public repo anymore.
# Todo
- better message detection
- diagflow AI bot
- image upload capabilities

Made by [@updatesvc](https://github.com/updatesvc/WhatsApee)


