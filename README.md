# Spotify-Music
ZygnalBot Spotify Music Extension, created by theholyonez. This extension brings a premium, seamless Spotify music experience directly to your Discord server, complete with an interactive player, robust admin controls, and high-quality audio playback.
> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)
# ZygnalBot Spotify Music Extension

Welcome to the official guide for the ZygnalBot Spotify Music Extension, created by theholyonez. This extension brings a premium, seamless Spotify music experience directly to your Discord server, complete with an interactive player, robust admin controls, and high-quality audio playback.

## ✨ Features

* **Full Spotify Integration**: Search for any song, artist, or paste a Spotify track/playlist link to start listening.
* **Interactive Music Player**: A clean, modern embed with buttons to control everything. No need to memorize complex commands!
* **High-Quality Audio**: Uses yt-dlp to find and stream the best audio quality for the tracks you love.
* **Advanced Queue System**: Add songs, view the upcoming queue, see recently played tracks, clear the queue, and even shuffle it for a random mix.

# Bot Setup Instructions

## Installation

Install the required Python packages:

pip install discord.py spotipy yt-dlp aiohttp PyNaCl

## FFmpeg Setup

You also need the `ffmpeg` executable in the root directory (e.g., where `Main.py` or `Main_bot_3.py` is located).

1. Download FFmpeg from one of the following sources:  
   - https://www.videohelp.com/software/ffmpeg  
   - https://winstall.app/apps/Gyan.FFmpeg.Essentials

2. Unzip the downloaded file.

3. Go to the `/bin` folder inside the unzipped directory and drag the `ffmpeg.exe` file to the same folder as your `Main.py` or `Main_bot_3.py`.



### Powerful Admin Controls

* **Role & Channel Restrictions**: Designate a specific "DJ" role or lock music commands to a single channel to keep your server organized.
* **Global Access Mode**: Allow everyone in the server to use the music commands, regardless of their roles.

### Flexible Spotify Credentials Setup

* **Bot Owner Global Setup**: The bot owner can set up global Spotify API keys that work across all servers.
* **Per-Server Setup**: If global keys aren't set, server owners can configure their own Spotify API keys for their server.

### Smart Playback

* The bot is smart! It knows when to resume paused music, play from the queue, or ask you to search for a song.

## 🚀 Getting Started: Command Flow

Using the music bot is designed to be simple and intuitive. Here's the typical flow for both admins setting it up and users playing music.

### 1. Server Setup (Admins Only)

Before anyone can play music, the bot needs to be configured.

* **Set up Spotify API Keys**: This is the most crucial step.

  * The Bot Owner can use `/spotify_setup` to set up global credentials for all servers.
  * If no global credentials exist, the Server Owner must use `/spotify_setup` to add keys for their specific server. The command will guide you on how to get a Client ID and Secret from the Spotify Developer Dashboard.

* **Configure Permissions (Optional)**: As a server admin, use the `/music_admin` command to customize how the bot works.

  * Want only certain people to play music? Use `/music_admin action: Set Music Role`.
  * Want to keep music commands in one place? Use `/music_admin action: Set Music Channel`.
  * Want everyone to be able to use the bot? Use `/music_admin action: Make Global`.

### 2. Playing Music (For Everyone)

Once the setup is done, playing music is easy!

* **Open the Player**: Type `/spotify`. This will bring up the main interactive music player.
* **Join a Voice Channel**:

  * First, make sure you are in a voice channel.
  * Click the 🎤 Join Voice button on the player to summon the bot to your channel.
* **Add a Song**:

  * Click the 🔍 Search & Add button. A pop-up will appear.
  * Type a song name, artist, or paste a Spotify URL (track or playlist) and submit.
  * If you searched by name, a list of results will appear. Click the button corresponding to the song you want.
* **Control Playback**:

  * Use the ▶️ Play, ⏸️ Stop, ⏯️ Pause/Resume, ⏭️ Next, and ⏮️ Previous buttons to control the music.
  * Click 📋 Queue to see what's playing, what's up next, and what was played recently.
* **Leave**: When you're done, click the 🔊 Leave Voice button to disconnect the bot and clear the queue.

## 📋 Command Details

### Admin Commands

#### /spotify\_setup

* **Who can use it?** Bot Owner and Server Owners.
* **What does it do?** Initiates the process of adding a Spotify Client ID and Client Secret, which are required for the bot to search for and play music. The bot owner has the option to set global keys, which prevents server owners from setting their own.

#### /music\_admin

* **Who can use it?** Server Administrators.
* **Sub-Commands (action):**

  * 🎯 Set Music Role: Restricts music commands to users who have a specific role.
  * 🌐 Make Global: Allows any user in the server to use the music commands. This overrides the music role setting.
  * 📍 Set Music Channel: Restricts the `/spotify` command and player to a single channel.
  * ❌ Remove Channel Restriction: Allows the `/spotify` command to be used in any channel.
  * ⚙️ View Current Settings: Shows the current configuration for the music role, global access, and music channel.

### User Command

#### /spotify

* **Who can use it?** Anyone, provided they meet the role/channel requirements set by the admins.
* **What does it do?** Spawns the main interactive player embed, which contains all the buttons you need for a complete music experience.

### Player Buttons

* 🎤 Join Voice: Summons the bot to your current voice channel.
* ▶️ Play: Starts playing from the queue, resumes a paused track, or opens the search modal if the queue is empty.
* ⏸️ Stop: Stops the music completely.
* ⏯️ Pause/Resume: Toggles between pausing and resuming the current song.
* ⏭️ Next: Skips the current song and plays the next one in the queue.
* ⏮️ Previous: Plays the previously played song.
* 📋 Queue: Shows the current song, the next 5 songs in the queue, and the 5 most recently played songs. From here, you can also clear or shuffle the queue.
* 🔍 Search & Add: Opens a pop-up to search for a song/playlist to add to the queue.
* 🔊 Leave Voice: Disconnects the bot from the voice channel and clears the queue.
