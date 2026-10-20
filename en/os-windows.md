# Windows 

## choco

The Package Manager for Windows
Modern Software Automation

https://chocolatey.org/install 

choco install chocolatey-compatibility.extension

## SoX

SoX is the Swiss Army Knife of sound processing utilities. It can convert audio files to other popular audio file types and also apply sound effects and filters during the conversion.
(used in # [Whisper Assistant Extension (Voice to text)](https://forum.cursor.com/t/whisper-assistant-extension-voice-to-text/784) )

https://sourceforge.net/projects/sox/ 

~~~
# Установка SoX (рекомендуется)
choco install sox.portable

# Если возникают проблемы, попробуйте версию 14.4.1
choco install sox.portable --version=14.4.1

# Альтернативно - ffmpeg
choco install ffmpeg

~~~

## Setting 

https://stackoverflow.com/questions/79260111/npx-file-c-program-files-nodejs-npx-ps1-cannot-be-loaded-because-running-scri

1. Open PowerShell as Administrator
    
2. Check Current Execution Policy
    
    `Get-ExecutionPolicy`
    
    If it shows Restricted, you need to change it.
    
3. Set Execution Policy to Unrestricted
    
    `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned`