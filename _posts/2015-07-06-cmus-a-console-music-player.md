---
layout: post
title: "CMUS, A console music player"
description: "A beginners guide for cmus"
category: "tools"
tags: [tools]
---
Its been a while since I've written my last post here. Meanwhile, I've been writing some posts on [fossbytes](http://www.fossbytes.com "Fossbytes"). Now, that I've again starting writing here, I am hoping to continue this in future too. 

Back on the topic, CMUS is a console application (those which you operate through text only, no mouse). Recently I've become a big fan of such applications. I use console text editor, file manager, and even web browser (occasionally). Its not that I am living in stone age days, or my system is not capable of running graphical application. Its just how quickly and beautifully your work is done with such applications. You don't have to take your fingers off the keyboard, ever, which is quite bothering for me. CMUS is one of those apps. 

CMUS is available on most distibution's official repositories. Alternatively, you can get it from [github](https://github.com/cmus/cmus). After installing it, type **cmus** in your terminal.

When you launch cmus, it presents the album/artist view. There are seven different views for various operations. You can switch between them by corresponding number (1-7).

- 1 for album/artist view
- 2 for library
- 3 for playlist
- 4 for queue
- 5 for file browser
- 6 for filters
- 7 for keybindings

### Adding Music
To add music, goto file browser (press 5). Go to a music file, and press **a** to add it into your library. Or add the complete music folder by taking highlight to that folder and pressing **a**. To play music, press **enter** on the desired file. Press 2 to go back to library. To remove a track from library, press **D**. 

### Creating playlist
Once you've added some tracks to your library, it's good to create a playlist, for your favourites. Move the highlight to desired track, and press **y** to add it to the playlist. You can access the playlist by pressing **3**.

### Queuing tracks
If you want to listen a track next to the playing one, add it to the queue. As soon as the current track finishes, cmus pops the next track from the queue and plays it. To do so, go on a track and press **e**. You can add multiple tracks to the queue and they will be processed in FIFO order. To view the current queue contents, press **4**. To remove a track from playlist or queue, switch to that view and press **D**, just as the library.

### Miscellaneous
- **b**: switch to next track
- **z**: switch to previous track
- **c**: toggle play/pause
- **v**: stop
- **x**: play
- **s**: toggle shuffle
- **C**: toggle continue
- **:q**: quit cmus

You can access cmus command line by pressing **:** and typing in appropriate command.

There is a thorough manual and a easy to learn beginner tutorial that ships with cmus. Type **man cmus** to access the manual, and **man cmus-tutorial** for the beginners guide.

For any suggestions or query, please post a comment.
