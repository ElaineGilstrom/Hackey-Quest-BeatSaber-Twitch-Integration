# Beat Saber Twitch Integration For The Quest

This is a simple irc bot that handles basic beat saber song requests. It 
works by creating a list of requested songs, then once the streamer is 
ready, will create a .bplist (beat saber playlist) that can easily be 
uploaded to bmbf.

### Setup ###

0. Configure the `.env` file (see Enviromental Variables for more info)
1. Install python 3.7+
2. Run `pip install pipenv`
3. Run `pipenv sync` in directory with bot.py
4. Run `pipenv shell` 
5. Finally, run `python bot.py` to start the bot.

Warning: git and pipenv like to fight, so I would recommend copying everything (with the exception of git) over to a new directory when running pipenv so git doesn't screw up the file permissions and cause pipenv to crash.

#### Enviromental Variables ####

Twitch Configuration:
1. `TMI_TOKEN` - The oauth token for your chatbot. You can get it here: https://twitchapps.com/tmi/
2. `CLIENT_ID` - Your bots username (must be in all lowercase letters)
3. `BOT_NICK` - Your bots nickname (it is easiest if you make this the same as its username)
4. `BOT_PREFIX` - the prefix for commands. It is easiest to just leave this as the default exclamation mark.
5. `CHANNEL` - Your channel name (must be in all lowercase letters)

BSR Configuration:
1. `MIN_SONG_APPROVAL` - The minimum like to dislike ratio to except a song into your queue. Default is 0.00 (aka anything goes). Range of `0.00 <= MIN_SONG_APPROVAL < 1.00` with 1.00 being 100% approval
2. `PLAYLIST_THUMBNAIL` - The PNG thumbnail to use for the playlists. MUST BE BASE64 ENCODED 
3. `OUTPUT_FOLDER` - The folder to save your queue playlists to.

Scoresaber Configuration:
1. `SCORESABER_ID` - Your scoresaber ID for the !ss command. Can be found in the url when looking at your scoresaber profile.

### Commands ###

0. `!help [cmd]` - Displays commands and gives more information about specific commands.
1. `!bsr <key>` - Adds the given song to the queue.
2. `!oops` - Removes the last song added by the caller from the queue.
3. `!queue` - Prints out the current songs in queue
4. `!history` - Prints out the songs that have already been packaged into playlist form.
5. `!ss` - Displays the streamer's scoresaber info.
6. `!code` - Responds with the link to this repository.


Streamer specific commands:

0. `!genlist` - Generates a beat saber playlist for the current queue and moves qued songs into history.
1. `!kill` - Kills the bot
