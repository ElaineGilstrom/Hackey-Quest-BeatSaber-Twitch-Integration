# Quest Hackey BSR/Twitch integration

This is a simple irc bot that handles basic beat saber song requests. It 
works by creating a list of requested songs, then once the streamer is 
ready, will create a .bplist (beat saber playlist) that can easily be 
uploaded to bmbf.

The current build is not working, but I will hopefully get it working soon. Just need to sort out the beatsaver api and finish testing.

#### Setup ####

0. Configure the `.env` file (see Enviromental Variables for more info)
1. Install python 3.7+
2. Run `pip install pipenv`
3. Run `pipenv --python 3.7` in directory with script
4. Run `pipenv sync` in directory with script
5. Run `pipenv shell` then `python bot.py`


###### Enviromental Variables ######

`TMI_TOKEN` - The oauth token for your chatbot. You can get it here: https://twitchapps.com/tmi/
`CLIENT_ID` - Your bots username (must be in all lowercase letters)
`BOT_NICK` - Your bots nickname (it is easiest if you make this the same as its username)
`BOT_PREFIX` - the prefix for commands. It is easiest to just leave this as the default exclamation mark.
`CHANNEL` - Your channel name (must be in all lowercase letters)

`MIN_SONG_APPROVAL` - The minimum like to dislike ratio to except a song into your queue. Default is 0.00 (aka anything goes)
`PLAYLIST_THUMBNAIL` - The PNG thumbnail to use for the playlists. MUST BE BASE64 ENCODED
`OUTPUT_FOLDER` - The folder to save your queue playlists to.

`SCORESABER_ID` - Your scoresaber ID for the !ss command.
