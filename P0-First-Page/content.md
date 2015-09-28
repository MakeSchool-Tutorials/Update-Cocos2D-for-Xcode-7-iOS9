---
title: "Update Cocos2D to support XCode 7!"
---

0. Tools - OK
1. Create SB project from scratch - OK
2. Publish project - OK
3. Download newest Cocos2D from github, provide link - OK
4. Copy cocos2d, cocos2d-ui and external folders - OK
5. replace them in the project folder - OK
6. open project in XCode - OK
7. change iOS targets in all subprojects to 6.0
8. clean entire project (incl. subprojects)
9. build and run to ensure function

Apple's release of XCode 7 brings Swift 2 and support for the latest versions of each of its platforms.  Need to say something here about SB being in stasis and unable to deliver cocos2d updated.

#Getting Started

Let's go through the steps required to bring a project up to the latest version of Cocos2d.  We'll start from the very beginning, from a brand new project created from SpriteBuilder.  If you are updating an existing project, I suggest trying it with a fresh project first.  

We need a few tools to create a new project with Cocos2D.  The first is Xcode 7, of course.  Its available on the [app store](https://itunes.apple.com/us/app/xcode/id497799835?mt=12).  SpriteBuilder is an open source tool that streamlines content creation and works with Cocos2D.  SpriteBuilder can be downloaded from the [app store](https://itunes.apple.com/us/app/spritebuilder/id784912885?mt=12) or from [www.spritebuilder.com](http://www.spritebuilder.com).  If you have SpriteBuilder already, verify it is the latest version (1.4.9). 

![](./spritebuilder_version.png)

With these tools we can begin.  Create a new project in SpriteBuilder, and publish it.  


#Update Cocos2D

Now that we have a project, we can go ahead and update the version of Cocos2D it is using.  Rather than rely on SpriteBuilder to perform the update, we'll do it manually.  To get the most up to date version, download the project straight from its repository located [here](https://github.com/cocos2d/cocos2d-objc).  If you want to clone the repository from the command line, the command is:

	git clone --recursive https://github.com/cocos2d/cocos2d-objc.git

This will download the latest version of Cocos2D (and its dependencies).  Now to update the project.  Navigate to the new version and copy three folders: cocos2d, cocos2d-ui and external.

![](./update_select.png)

> [info]
> You can hold command (⌘) to select multiple folders at once.

These three folders contain the changes that need to be moved into the project.  The next part is finding the location of Cocos2D in your project.  It's located in the folder named "cocos2d-iphone" inside the project.  Pasting the new folders will prompt a warning that you are trying to replace folders that exist already.  No files or subfolders were renamed, so doing this OK.  It won't break anything.

![](./copy_folders.gif)

With the new folders in place, we can move over and tie things up in XCode.  

#Cleanup and Build


