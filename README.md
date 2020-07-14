# EPT-bot

This bot is still work in process. It is a fork of [igCTF](https://gitlab.com/inequationgroup/igCTF), which is again a fork of [NullCTF](https://github.com/NullPxl/NullCTF).

## Install

### develop

```bash
cd cloned-directory
virtualenv venv -p python3
source venv/bin/activate
pip install -r requirements.txt
```

### build

`docker-comopse up --build`

### start

`docker-compose up`

## How to Use

> This bot has commands for encoding/decoding, ciphers, and other commonly accessed tools during CTFs. But, the main use for igCTF is to easily set up a CTF for your discord server to play as a team. The following commands listed are probably going to be used the most.

- `!create "ctf name"` This is the command you'll use when you want to begin a new CTF. This command will make a text channel with your supplied name under the category 'CTF' (If the category doesn't exist it will be created). _Must have permissions to manage channels_

_NOTE: the following ctf specific commands will only be accepted under the channel created for that ctf. This is to avoid clashes with multiple ctfs going on in the same server._

- `!ctf join/leave` Using this command will either give or remove the role of a created ctf to/from you.
    ![enter image description here](https://i.imgur.com/4QPUgvM.png)

- `!ctf challenge add/working/solved "challenge name"` Allows users to add challenges to a list, and then set the status of that challenge. _Use quotations_

- `!ctf challenge list` This is the list command that was previously mentioned, it displays the added challenges, who's working on what, and if a challenge is solved (and by who).
    ![enter image description here](https://i.imgur.com/KH5dYZr.png)

- `!ctf end` Delete the ctf info from the db, and remove the role from your server. _Must have permissions to manage channels_

---

> The following commands use the api from [ctftime](https://ctftime.org/api)

- `!ctftime countdown/timeleft` Countdown will return when a selected CTF starts, and timeleft will return when any currently running CTFs end in the form of days hours minutes and seconds.
    ![enter image description here](https://i.imgur.com/LFSTr33.png)
    ![enter image description here](https://i.imgur.com/AkBfp6E.png)

- `!ctftime upcoming <number>` Uses the api mentioned to return an embed up to 5 upcoming CTFs. If no number is provided the default is 3.
    ![enter image description here](https://i.imgur.com/UpouneO.png)

- `!ctftime current` Displays any currently running CTFs in the same embed as previously mentioned.
    ![enter image description here](https://i.imgur.com/RCh3xg6.png)

- `!ctftime top <year>` Shows the ctftime leaderboards from a certain year _(dates back to 2011)_.
    ![enter image description here](https://i.imgur.com/2npW7gM.png)

---

> Utility commands

- `!magicb filetype` Returns the mime and magicbytes of your supplied filetype. Useful for stegonography challenges where a filetype is corrupt.

- `!rot "a message" <right/left>` Returns all 25 possible rotations for a message with an optional direction (defaults to left).

- `!b64 encode/decode "message"` Encode or decode in base64 _(at the time of writing this, if there are any unprintable characters this command will not work, this goes for all encoding/decoding commands)._

- `!binary encode/decode "message"` Encode or decode in binary.

- `!hex encode/decode "message"` Encode or decode in hex.

- `!url encode/decode "message"` Encode or decode with url parse. This could be used for generating XSS payloads.

- `!reverse "message"` Reverse a message.

- `!counteach "message"` Count the occurrences of each character in the supplied message.

- `!characters "message"` Count the amount of characters in your message.

- `!wordcount a test` Counts the amount of words in your message (don't use quotations).

- `!htb` Return when the next hackthebox machine is going live from @hackthebox_eu on twitter.

- `!cointoss` Get a 50/50 cointoss to make all your life's decisions.

- `!request/report "a feature"/"a bug"` Dm's the creator with your feature/bug request/report.

- `!help pagenumber` Returns the help page of your supplied number (currently there are 2 pages)

> ### Have a feature request? Make a GitHub issue or use the >request command
