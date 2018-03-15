---
title: Backing up files up with Symbolic Links
layout: post
date: '2018-03-10'
author: Joshua Galan
cover: /blog/assets/img/symbolic-links/header.png
tags: windows terminal
---

> Today I will teach you how your files can exist in two places at once.

Being organized and having things easily accessible is crucial to my work flow. I truly loathe not being able to locate something in a punctual manner because it subtracts from the time I can be doing something productive.  As someone who works from his laptop often as an autodidact, it's imperative I'm able to preserve my motivation and kick things into gear with minimal effort. 

One of the ways I accomplish this is by pinning my most frequently used folders and applications to my Windows start menu. By simply tapping the Windows key, I'm instantly greeted with a buffet of my favorites. One of which, happens to be my **Web Design** folder, which contains the majority of my code-related projects. 

![](/blog/assets/img/symbolic-links/winmenu.png)

Although this achieves my main purpose, the paranoia and OCD in me prefers to up the ante. I want to be able to have these files backed up on my cloud in case I want to access them from another computer or if my laptop takes a nose dive. I'm sure anyone who's had the misfortune of losing digital work wishes they had a duplicate stored safely somewhere else.

## Symbolic Links 

One of my favorite methods for file backups involves synchronizing my files in real-time with Dropbox by using symbolic links.

Symbolic links are files that reference to another file or folder. Think of it as a “shortcut” for your files that you can access from a different location. Any changes made to files contained within a symbolic link folder will also apply to a secondary folder of your choosing. I prefer to synchronize my PC folders with Dropbox for accessibility from my mobile device or another computer.

## Setting Up Your Links (Windows)
### 1. Open Command Prompt as Administrator.
This can be achieved by pressing the Windows Key + X and clicking on Command Prompt (Admin) or performing a search for Command Prompt, right-clicking it and Run as Administrator when finding it.

![](/blog/assets/img/symbolic-links/cmd-admin.png)
*Windows Key + X then click on Command Prompt (Admin)*

### 2. Establishing folders to be synced.
With Command Prompt open, we’re going to first type `move` followed by the path for the folder you want to sync. Then type in the path to your Dropbox folder. Remember to use quotations for both paths.

`move “C:\Path\To\PCFolder” “C:\Users\NAME\DropBox”`

![](/blog/assets/img/symbolic-links/cmd-move.png)
*This is how it looks on my terminal. (I’m moving a “Sample Folder” located in My Documents to Dropbox.)*

### 3. Syncing your folders 
Now we’re going to create a symbolic link for the original folder moved from your PC to the one currently on your Dropbox. Type in the below command (modifying your paths accordingly) into Command Prompt. After this process is complete you will have two identical folders (one on your PC and the other on Dropbox) that are both synchronized to each other.

`mklink /d “C:\Path\To\PCFolder” “C:\Users\NAME\Dropbox\PCFolder”`

![](/blog/assets/img/symbolic-links/cmd-sync.png)
*In this example, both my Sample Folder (located on my computer) and a copy of the Sample Folder have been synchronized on my Dropbox account. Whatever I modify inside the Sample Folder will now be available in both locations.*

### Example Use Cases
Below are a few ideas on how you may benefit from symbolic links with 
cloud synchronization.

- **Photos** 
Whether you’re a photographer, graphic designer, or just want to keep track of your images — your files will be available on the cloud.

- **Word / Excel** 
Are you typing up an essay or an important contract? How about crunching numbers for your business or personal spreadsheet? This method will save a duplicate copy.

- **Code Editing** 
This is my primary reason for using this symbolic links. Whenever I edit a file related to code (HTML/CSS/JavaScript); I know I’ll have a copy automatically synced to Dropbox.

Keep in mind you can use symbolic links for any files you wish. One caveat to consider is be cognizant of how much storage space is available on your Dropbox account in relation to the size of the files you’re synchronizing.

---

Did you find this article interesting or useful? Show me love by sharing it or commenting!

Want to stay updated on my future blog articles? Subscribe to my e-mail list below.