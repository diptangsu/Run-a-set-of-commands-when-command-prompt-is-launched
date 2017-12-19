# Run-a-set-of-commands-when-command-prompt-is-launched

To run a set of commands everytime the command prompt is launched, an init script can be specified in the AutoRun registry value.

## Prerequisites
You need to have a computer running Windows for this to work.

## Getting Started
Launch cmd and run this command:
```
reg add "HKCU\Software\Microsoft\Command Processor" /v AutoRun ^ /t REG_EXPAND_SZ /d "%"USERPROFILE"%\init.cmd" /f
```

**Copy paste the file init.cmd in the location** ```%USERPROFILE%\``` which is usually C:\Users\username
To navigate to this location, *simply type in %USERPROFILE%\ in the RUN dialogue box (Windows Key + R) and hit enter*.

Or you can also create your own init.cmd file. I simply created a .txt file called init.txt and changed the extension to .cmd
Here is what you can write in the file.
```
echo off
<command 1>
<command 2>
<command 3>
...
echo on
```
Just type in all the commands which you want to execute everytime the command prompt is launched.

## Undoing Changes
To remove these changes, delete the registry key by running the following command in cmd:
```
reg delete "HKCU\Software\Microsoft\Command Processor" /v AutoRun
```

## P.S.
* I don't know much about what I should be doing so I just used it to print my own name lol.
* If you want to view my init.cmd file, simply change its extension to .txt and open it using any text editor.

## Here is how my cmd looks when launched
![Example](https://github.com/diptangsu/Run-a-set-of-commands-when-command-prompt-is-launched/blob/master/Preview.JPG)
