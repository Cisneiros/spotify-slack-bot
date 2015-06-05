# Spotify-Slack-Bot

*Bring life to your office with a collaborative playlist controlled via Slack!*

Spotify-Slack-Bot is a Slack bot that controls an instance of Spotify.  It can tell what song is playing and control playback (e.g. playing and pausing).  Run it on a machine with Spotify installed and connected to your office speakers, create a collaborative playlist that your team can add songs to and you have some nice music on your office that can be easily paused by anyone when some quiet time is needed, and managed without needing physical access to the computer running Spotify.

## Features

* Tells anyone which song is playing via Private Message (not to disturb anyone else).
* Controls playback: play, pause and skip a song.
* When controlling playback, it broadcasts on a dedicated Slack channel so everyone knows who is messing with the music.

For now, there is no way to add songs to the playlist or to the play queue.  Adding to the playlist could be done by integrating with Spotify's Web API, but there is no way to queue songs as far as I'm aware.

## What you need

* A computer (OS X only, for now) running Spotify, with a collaborative playlist.
* Python (already included with OS X), `pip` and `virtualenv`.
* A Slack Bot integration setup and its API Key.
* A Slack channel dedicated to your playlist for the bot to broadcast messages when needed.

## Installing

If you don't have `pip`, you can get it with:

```shell
sudo easy_install pip
```

If you don't have `virtualenv`:

```shell
sudo pip install virtualenv
```

Clone the repository on your machine.  Then, create a virtual environment for managing dependencies.

```shell
virtualenv venv
```

Activate the virtual environment.

```shell
source venv/bin/activate
```

Install the dependencies.

```shell
pip install -r requirements.txt
```

## Configuring and Running

Make sure you have the following environment variables set:

* `SPOTIFYSLACK_SLACK_API_KEY`: your Bot integration API Key.
* `SPOTIFYSLACK_SLACK_BROADCAST_CHANNEL`: the Channel ID for your broadcast channel.

Then, if you haven't already for this session, activate the virtual environment.

```shell
source venv/bin/activate
```

Finally, run it.

```shell
python spotify.py
```

## TO-DOs:

Non-exhaustive unordered list of future steps:

* Search for songs and add to the collaborative playlist.
* Add a song to the queue (depends on Spotify adding support on AppleScript API).
* Supporting other operating systems (see below).
* Package this nicely for a friendlier installation and usage.

Feel free to contribute by implementing any of these features, implementing any anything else you may think of or fixing any bugs.

## Why OS X only?

The bot uses AppleScript to talk to the Spotify client running on the computer.  The name kinda makes it obvious it is not supported on non-Apple operating systems.  As the office I work on had Spotify running on a Mac already, that was not an issue at the time.  There might be ways to control and get data from the player on Windows and Linux, I just haven't done any research on it for now.

## License: MIT

Copyright © 2015 Alexandre Cisneiros - www.cisneiros.com

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.  IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
