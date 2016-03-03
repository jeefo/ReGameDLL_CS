# ReGameDLL_CS
Reverse-engineered gamedll (mp.dll / Counter-Strike)

## What is this?
Regamedll_CS is a result of reverse engineering of original library mods HLDS (build 6153beta) using DWARF debug info embedded into linux version of HLDS, cs.so

At the moment, the work of reverse engineering continues

## Goals of the project
* Provide more stable (than official) version of Counter-Strike game with extended API for mods and plugins

## How can use it?
Regamedll_CS is fully compatible with official mod CS 1.6 by Valve. All you have to do is to download binaries and replace original mo.dll/cs.so

Compiled binaries are available here: http://nexus.rehlds.org/nexus/content/repositories/regamedll-snapshots/regamedll/regamedll/0.2-SNAPSHOT/

Archive's bin directory contains 2 subdirectories, 'bugfixed' and 'pure'
* 'pure' version is designed to work exactly as official mod CS
* 'bugfixed' version contains some fixes and improvements

<b>Warning!</b> Regamedll_CS is not binary compatible with original hlds since it's compiled with compilers other than ones used for original mod CS. This means that plugins that do binary code analysis (Orpheu for example) probably will not work with Regamedll_CS.

## Current status
* Counter-Strike 1.6 - 100%
* Counter-Strike: Condition Zero - 100%

## How to install zBot for CS 1.6?
* Extract all the files from an [archive](regamedll/extra/zBot/bot_profiles.zip?raw=true)
* Enter '-bots' option at the command line HLDS

## Build instructions
There are several software requirements for building rehlds:
<ol>
<li>Java Development Kit (JDK) 7+ (http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)</li>
<li>For Windows: Visual Studio 2013 and later</li>
<li>For Linux: Intel C++ Compiler 13 and later</li>
</ol>

### Checking requirements
####JDK version
Windows<pre>&gt; %JAVA_HOME%\bin\javac -version
javac 1.8.0_25
</pre>

Linux
<pre>$ javac -version
javac 1.7.0_65
</pre>

####Visual Studio
Help -> About

####ICC
<pre>$ icc --version
icc (ICC) 15.0.1 20141023
</pre>

### Building
On Windows:
<pre>gradlew --max-workers=1 clean buildRelease</pre>

On Linux:
<pre>./gradlew --max-workers=1 clean buildRelease</pre>

Compiled binaries will be placed in the build/binaries/ directory

### Credits
Thanks to the project [ReHLDS](https://github.com/dreamstalker/rehlds) ( ReGameDLL_CS was created on the basis of ReHLDS )
