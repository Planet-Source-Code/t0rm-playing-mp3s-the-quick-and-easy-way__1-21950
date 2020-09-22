<div align="center">

## Playing MP3s \- the quick and easy way


</div>

### Description

Play, stop, and pause MP3's with these simple functions!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[$t0rm](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/t0rm.md)
**Level**          |Beginner
**User Rating**    |3.7 (11 globes from 3 users)
**Compatibility**  |VB 5\.0, VB 6\.0
**Category**       |[Sound/MP3](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/sound-mp3__1-45.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/t0rm-playing-mp3s-the-quick-and-easy-way__1-21950/archive/master.zip)





### Source Code

While browsing PSC to figure out how to make an MP3 player, all I saw were big huge ZIP files with skins and stuff. After sifting through that code, I made a library to simplify the playing/pausing/stopping of MP3s. Put all this in a module called MP3Player:<br>
==========================================<br>
<pre>
Private Declare Function mciSendString Lib "winmm.dll" Alias "mciSendStringA" (ByVal lpstrCommand As String, ByVal lpstrReturnString As String, ByVal uReturnLength As Long, ByVal hwndCallback As Long) As Long
Public Sub PlayMP3(filename As String)
 mciSendString "Open " & filename & " Alias MM", 0, 0, 0
 mciSendString "Play MM", 0, 0, 0
End Sub
Public Sub PauseMP3()
 mciSendString "Stop MM", 0, 0, 0
End Sub
Public Sub StopMP3()
 mciSendString "Stop MM", 0, 0, 0
 mciSendString "Close MM", 0, 0, 0
End Sub</pre><br>
==========================================<br>
When playing a file, if it has spaces in the name, be sure to surround it with Chr(34)!
If you can't figure out how to use those, then you obviously aren't worthy of using them :)

