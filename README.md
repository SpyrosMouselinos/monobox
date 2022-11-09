<p align="center">
  <img src="https://github.com/ozzs/musicPlayer/blob/main/assets/MonoBoxLogo.png" alt="MusicPlayerLogo" width="300">
  <br />

  <h4 align="center">A lightweight, self-hosted, ad-free player to play music from your local library on your mobile device, in a friendly and simple UI.</h4>
  <br />
</p>

<p align="center">
  <img alt="React-Native" src="https://img.shields.io/badge/react_native-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" />
  <img alt="Javascript" src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" />
  <img alt="TypeScript" src="https://img.shields.io/badge/-TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" />
  <img alt="Prettier" src="https://img.shields.io/badge/-Prettier-F7B93E?style=for-the-badge&logo=prettier&logoColor=white" />
  <img alt="Python" src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" />
  <img alt="FastAPI" src="https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi" />
  <img alt="SQLite" src="https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white" />
</p>

## Table of Content
- [Overview](#overview)
  - [Technologies and Libraries](#technologies-and-libraries)
- [Key Features](#key-features)
- [Installation](#installation)
  - [Backend Setup](#backend-setup)
  - [Frontend Setup](#frontend-setup)
- [How To Use](#how-to-use)
  - [Create Playlist](#create-playlist)
  - [Add Songs To Playlist](#add-songs-to-playlist)
  - [Remove Songs From Playlist](#remove-songs-from-playlist)
  - [Delete Playlist](#delete-playlist)
  - [The Songs Carousel](#the-songs-carousel)
  - [Toggle Themes](#toggle-themes)
- [Support](#support)

## Overview
MonoBox is a free music application designed to be easy to operate, intuitive to the user and has fast performance. <br />
Its main purpose is to play the music files you have on your computer, and to allow you to create and customize playlists according to your personal taste. <br />

MonoBox is a self-hosted fullstack application built using the latest and most sought-after technologies and libraries on the market. <br />
Users will be able to run their own servers with their own songs. The server itself is implemented in **Python** and the mobile application in **React-Native**. <br />

### Technologies and Libraries
#### Frontend
* **React-Native** :iphone:
  - _Javascript & Typescript_
  - Code formatted with _Prettier_ :ribbon:
  - _React Native Track Player -_ An audio module for music apps :musical_note:
  - _React Query -_ A powerful library containing hooks for fetching, caching and updating asynchronous data
#### Backend
* **Python** :snake:
  - _FastAPI -_ A modern, fast (high-performance), web framework for building APIs with Python 3.7+ based on standard Python type hints 
  - _SQLModel -_ A library for interacting with SQL databases from Python code, with Python objects
  - _pre-commit_, _black_, _mypy_ and _isort_ are integrated to make sure the code looks good and clean
* **Database** :page_facing_up:
  - _SQLite_

## Key Features
* Simple & Easy to use music player
* Listen from your local library
* Create and customize your own playlists
* Open-Source code
* Dark / Light themes
* No ads

## Installation
First and foremost, make sure your mobile device and PC are using the same wireless network, 
otherwise the application will not be able to communicate with the server running on the computer.
<br /> <br />
Then, in the root of the project, create 2 folders: 
* ``songs`` contains all the songs in the app library.
* ``covers`` contains all the artworks of the songs in the ``songs`` folder.

Now you can copy all the songs you want to display in the app into the ``songs`` folder.

### Backend Setup
From the root, you need to navigate to the ``backend`` folder. from your terminal:
```
cd backend
```

The ``requirements.txt`` file lists all the Python libraries that the music player depends on, and they can be installed from your terminal using:
```
pip install -r requirements.txt
```

Then, in the ``main.py`` file, you have this block of code, where you need to insert your PC's IP address (notice the comment):
```python
host_ip = "0.0.0.0" # Change to your PC's IP
host_port = 5000
music_folder_url = "..\songs"
cover_folder_url = "..\covers"
```
The default port is 5000, but you can also change it if you want the server to listen to a different port, 
although it is required to change this in the Frontend as well.
<br /> <br />
Finally, run the following command from your terminal to set up your server and create your database:
```
python main.py
```

### Frontend Setup
After setting up the Backend, open a new terminal for the Frontend.
<br />
The ``package.json`` file lists all the React / React-Native libraries that the music player depends on, so let's install them from the terminal using:
```
npm install
```

In order for the application to communicate with the server in the Backend, we need to insert the PC's IP address to the Frontend as well.
<br />
So now we need to navigate to the ``mobile/utils`` folder from the root of the project, and then to the ``BaseAPI.tsx`` file.
<br />
Inside ``BaseAPI.tsx`` you have the following block of code, where you need to insert the same IP address as you did in the Backend (notice the comment):
```js
export const BASE_API_URL = '0.0.0.0' // Change to your PC's IP
export const BASE_API_PORT = 5000
```
If you decided to change the default port in ``main.py``, this is the place to change it as well.
<br /> <br />
Now you're all set!
<br />
You are welcome to try the application yourself or continue to the next section to learn about its features and how to use it.

## How To Use
### Create Playlist
Upon initializtion, in your _Homescreen_, you'll notice you have a playlist called _Liked Songs_ which does not contain any songs at the moment. Don't worry, we'll get to that later. :leftwards_arrow_with_hook: <br />
On the top right corner you'll also notice a :heavy_plus_sign: sign button, with which you can create a new playlist and give it a name! 
<br />
***INSERT: Homescreen GIF, create 2 new playlists***

### Add Songs To Playlist
If you followed the instructions on the [Installation section](#installation) and copied all the songs to the designated folder, you should be able to see all of them on your _Library_ screen. :books: <br />
In order to add a song to a playlist, press the button that appears to the right of each song, and choose one of your playlists. Pretty easy so far, huh? :v: <br /> <br />
***INSERT: Homescreen GIF, move to Library screen, add 2 songs to each new playlist and move back to Homescreen***

### Remove Songs From Playlist
So in order for you to remove a song from a playlist - simply press a song in a playlist and hold it for 2 seconds, and the song will be removed.
<br />
***INSERT: Homescreen GIF, remove one song from each playlist***

### Delete Playlist
The same goes for the entire playlist - press its name and hold for 2 seconds, and it will be deleted along with its songs.
<br />
***INSERT: Homescreen GIF, delete both playlists***

### The Songs Carousel
What music app would it be without a _Songs Carousel_, right?
For you to get to the _Songs Carousel_, just press on any song in a playlist, on any screen you'd like (e.g. Choosing a song from the _Library_ screen will create a queue of all the songs from the _Library_ for you).

### Toggle Themes
As mentioned before, you can switch themes between dark mode and light mode, using the moon icon that appears at the top right corner of the navigation drawer.

#### Oh, and one more thing!
In case you were wondering how the matter of adding/deleting songs works behind the scenes: <br /> 
Every 30 seconds, the server simultaneously checks for compatibility between the song lists in the ``songs`` folder and the database, and for each song one of the following actions is performed:
* If the song exists only in ``songs`` and not in the database :arrow_right: adds the song to the database.
* If the song exists only in the database and not in ``songs`` :arrow_right: deletes the song from the database.
* If the song exists both in the database and in the folder :arrow_right: does nothing.

Or in a more "Pythonic" way, if you'd like:
```python
if song in songs_folder and song not in database:
  database.append(song)
if song not in songs_folder and song in database:
  database.remove(song)
if song in songs_folder and song in database:
  continue
```

## Support
The product is still in its initial stages, so we would really appreciate feedback and donations 😄 <br />
And don't forget to star us — it motivates us a lot! :star:

### Project resources
* <a href="https://github.com/ozzs/musicPlayer">Source Code</a>
* <a href="https://react-native-track-player.js.org">React Native Track Player</a>
* <a href="https://tanstack.com/query/v4/?from=reactQueryV3&original=https://react-query-v3.tanstack.com">React-Query</a>
* <a href="https://sqlmodel.tiangolo.com">SQLModel</a>
* <a href="https://fastapi.tiangolo.com">FastAPI</a>

### Create a bug report or submit a feature request
If you see an error message or run into an issue, or maybe you have an idea, or you're missing a capability that would make development easier and more robust, please [create a bug report or submit a feature request](https://github.com/ozzs/monobox/issues/new). <br /> <br />
If a similar feature request already exists, don't forget to leave a "+1".
If you add some more information such as your thoughts and vision about the feature, your comments will be embraced warmly 😃
