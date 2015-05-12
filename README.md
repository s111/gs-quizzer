# Quizzer
Quizzer is a simple quiz game.
There is no limit to how many players there can be in a game.
The objective of the game is to answer the questions during a set time limit.
The three first players to select the correct option gets scored, the first one to answer gets more points than the next one and so on.
When all of the questions have been answered, the game ends and the scores are displayed, showing the top three players.

## Table of Contents

- [Precompiled](#precompiled)
- [Develop](#develop)
- [Compile and package](#compile-and-package)
- [Screenshots](#screenshots)
	- [Launcher](#launcher)
	- [Controller](#controller)

## Precompiled
The game packaged together with the controller.  
[All Releases](https://github.com/s111/gs-quizzer/releases)

Unzip and the ```quizzer``` folder can now be added to the game systems ```games``` directory.

## Develop
Download the repository:
```sh
git clone github.com/s111/gs-quizzer
```

Import the project into your IDE of choice. Choose a new maven project and import the pom.xml file. For your IDE to be able to compile the games, you first need to have maven generate the native libraries needed by the game. You do this by executing the following command:
```sh
mvn generate-resources
```
Then you need to set VM options to ```-Djava.library.path=target/natives```.

You should now be able to launch the game from your IDE. Remember that you need the game system running in the background for it to work.

## Compile and package
To package the game for distribuiton you must execute the following command:
```sh
mvn clean compile assembly:single
```

Now create this folder structure:  
```sh
quizzer/bin
```
Copy ```game.json```, ```screenshot.png``` and the ```controller``` folder into the ```quizzer``` folder. Copy the ```target/natives``` folder into it too and rename it to ```lib```. Now copy the jar file in the ```target``` folder into the ```quizzer/bin``` folder and rename it to ```quizzer.jar```.

You should now have a folder named ```quizzer``` which looks something like this:
```
quizzer/game.json
quizzer/controller/index.html
quizzer/controller/controller.js
quizzer/bin/quizzer.jar
quizzer/lib/lwjgl.dll
quizzer/lib/...
```
This folder can now be added to the game systems ```games``` directory.

## Screenshots

### Launcher
<img src="https://github.com/s111/gamesystem/blob/master/screenshots/quizzer.png" width="640">

### Controller
<img src="https://github.com/s111/gamesystem/blob/master/screenshots/quizzer_controller.png" width="320">
