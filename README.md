<a href="https://nodei.co/npm/discord-image-generation/"><img src="https://nodei.co/npm/discord-image-generation.png?downloads=true&downloadRank=true&stars=true"></a>

<a href="https://discord.gg/qvzwqaM"><img src="https://discord.com/api/guilds/661897530459684865/widget.png" alt="Discord server"/></a>

# discord-image-generation

A powerfull module that allow you to generate awesome images.

# Bugs and glitches

Feel free to report all bugs and glitches by creating an issue in the <a href="https://github.com/Mr-KayJayDee/discord-image-generation/issues">issue section.</a>

A correct and understandable issue contains : 
- Steps to reproduce 
- Code that summonned the error
- The complete error

You can also join me on my <a href="https://discord.gg/qvzwqaM">discord server.</a>

# Download

You can download it from <a href="https://www.npmjs.com/package/discord-image-generation">npmjs</a>.

```cli
npm i discord-image-generation
```

# Configuration

The first step is to import the module in your code.

```js
const DIG = require("discord-image-generation");
```

Then you have to request your image and send it as an attachement.

```js
// Import the discord.js library.
const Discord = require("discord.js")
// Create a new discord.js client.
const bot = new Discord.Client()

const DIG = require("discord-image-generation");

// Listen to the ready event
bot.on("ready", () => {
    console.log("ok");  
})

// Listen to the message event
bot.on("message", async (message) => {
    if (message.content === "*delete") {
        // Get the avatarUrl of the user
        let avatar = message.author.displayAvatarURL({ dynamic: false, format: 'png' });
        // Make the image
        let img = await new DIG.delete().getImage(avatar)
        // Add the image as an attachement
        let attach = new Discord.MessageAttachment(img, "delete.png");;
        message.channel.send(attach)
    }
})

// Log in to the bot
bot.login("super_secret_token")
````

# Available images


## Filters

- ``new Blur().getImage(`<Avatar>`, `<Level(Number)>`);``

![Blur](https://imgur.com/JqpNFTY.png)

- ``new Gay().getImage(`<Avatar>`);``

![Gay](https://imgur.com/BDTrXzZ.png)

- ``new Greyscale().getImage(`<Avatar>`);``

![Greyscale](https://imgur.com/h3ahY7Z.png)

- ``new Invert().getImage(`<Avatar>`);``

![Invert](https://imgur.com/Rl0wGQM.png)

- ``new Sepia().getImage(`<Avatar>`);``

![Sepia](https://imgur.com/OTbKVtj.png)


## Gifs

- ``new Blink().getImage(`<Avatar>`, `<Avatar2>`, <Timeout (Number in ms)>)``

![Blink](https://imgur.com/JjUXmRU.gif)

- ``new Triggered().getImage(`<Avatar>`);``

![Triggered](https://imgur.com/0QvyYQa.gif)


## Montage

- ``new Affect().getImage(`<Avatar>`);``

![Affect](https://imgur.com/g4Gaehb.png)

- ``new Batslap().getImage(`<Avatar>`, `<Avatar2>`);``

![Batslap](https://imgur.com/oYMpa5A.png)

- ``new Beautiful().getImage(`<Avatar>`);``

![Beautiful](https://imgur.com/HGZkmXo.png)

- ``new Bed().getImage(`<Avatar>`, `<Avatar2>`);``

![Bed](https://imgur.com/b1idSnr.png)

- ``new Delete().getImage(`<Avatar>`);``

![Delete](https://imgur.com/6V1IYJp.png)

- ``new Facepalm().getImage(`<Avatar>`);``

![Facepalm](https://imgur.com/cdPC3P1.png)

- ``new Hitler().getImage(`<Avatar>`);``

![Hitler](https://imgur.com/wK9puxH.png)

- ``new Jail().getImage(`<Avatar>`);``

![Jail](https://imgur.com/QslACNo.png)

- ``new Kiss().getImage(`<Avatar>`, `<Avatar2>`);``

![Kiss](https://imgur.com/sSoCAeH.png)

- ``new Mms().getImage(`<Avatar>`);``

![MMS](https://imgur.com/nH3URHb.png)

- ``new Rip().getImage(`<Avatar>`);``

![RIP](https://imgur.com/MgsRH8o.png)

- ``new Spank().getImage(`<Avatar>`, `<Avatar2>`);``

![Spank](https://imgur.com/VRvogo7.png)

- ``new Tatoo().getImage(`<Avatar>`)``

![Tatoo](https://imgur.com/wJju4UJ.png)

- ``new Thomas().getImage(`<Avatar>`);``

![Thomas](https://imgur.com/7R37J2j.png)

- ``new Trash().getImage(`<Avatar>`);``

![Trash](https://imgur.com/nwAHGgF.png)

- ``new Wanted().getImage(`<Avatar>`, `<Currency>`);``

> Currency ($, €, ...)

![Wanted](https://imgur.com/SFGRvSK.png)


## Utils

- ``new Circle().getImage(`<Avatar>`);``

![Circle](https://imgur.com/0Zo8NYS.png)

- ``new Color().getImage(`<Color>`);``

> An hex color is needed, like "#FF0000"

![Color](https://imgur.com/40tMwfe.png)

# Changelog 

## v1.0.0
- Changed the full structure
    - Sorted all files in folders
    - Sorted all files in the README
- Fixed new Wanted() text bug
- Added new Blink()
- Added a timeout options for new Triggered()
- Fixed the triggered example not animated
- Added some keywords
- Bumped jimp from ^0.12.1 to ^0.13.0
- Added workflow to auto publish to npm and github packages on push


## v0.1.14
- Updated .thomas() example

## v0.1.13
- Added example for .tatoo()
- Fixed the litle hole at the top of the users pic on .thomas()

## v0.1.12
- Saved all examples to imgur

## v0.1.11
- Added .tatoo()
- Updated JSDoc

## v0.1.9
- Added options for the wanted.
    - The base image has been updated
    - There is now a random price diplayed
    - You can now configure a currency
- Added .thomas()