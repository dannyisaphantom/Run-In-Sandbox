# Run-In-Sandbox
Run things in Windows Sandbox

How to run a Powershell Script as admin:

> You can create a batch file (*.bat) that runs your powershell script with administrative privileges when double-clicked. In this way, you do not need to change anything in your powershell script.To do this, create a batch file with the same name and location of your powershell script and then put the following content in it:

```
@echo off

set scriptFileName=%~n0
set scriptFolderPath=%~dp0
set powershellScriptFileName=%scriptFileName%.ps1

powershell -Command "Start-Process powershell \"-ExecutionPolicy Bypass -NoProfile -NoExit -Command `\"cd \`\"%scriptFolderPath%`\"; & \`\".\%powershellScriptFileName%\`\"`\"\" -Verb RunAs"
```
