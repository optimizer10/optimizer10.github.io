---
layout: page
title: Remove Windows Built-in Apps
description: How to remove Windows Built-in Apps in Windows 10 using Powershell
---

<style>
  h1, h2, h3, h4, h5 ,h6 {
    color: rgba(255,255,255,0.8);
  }
</style>

*Method compatible with Windows 10 2004*

<img src="/wiki/images/remove-windows-apps-1.png">

***Windows 10 comes with a lot of pre-installed apps that you can't simply uninstall with a finger touch.*** Most users don't need to use all of them so here's how to remove them by using Powershell.

<img src="/wiki/images/remove-windows-apps-2.png">

Powershell is a command interpreter made by Microsoft built into Windows 10 that allows you to do many awesome things including managing installed apps. To open it, open search from the taskbar and type the phrase ***"powershell"***. Click on the result with the right mouse button and from the pop-up menu select ***Run as administrator***.

It's not recommended to uninstall all the built-in apps as some of them are integral parts of the OS. But here's a list of apps and commands that you can use to uninstall the safe ones. Copy commands of your interest into the command line and execute them. These commands apply to all users.

<div style="background: #70707070; border-radius: 5px; padding: 10px;">
<p>
<b>Alarm App:</b> Get-AppxPackage -allusers  Microsoft.WindowsAlarms | Remove-AppxPackage
</p>

<p>
<b>Calculator App:</b> Get-AppxPackage -allusers Microsoft.WindowsCalculator | Remove-AppxPackage
</p>

<p>
<b>Camera App:</b> Get-AppxPackage -allusers Microsoft.WindowsCamera | Remove-AppxPackage
</p>

<p>
<b>Feedback Hub App:</b> Get-AppxPackage -allusers  Microsoft.WindowsFeedbackHub | Remove-AppxPackage
</p>

<p>
<b>Get Help App:</b> Get-AppxPackage -allusers Microsoft.GetHelp | Remove-AppxPackage
</p>

<p>
<b>Get Started App:</b> Get-AppxPackage -allusers  Microsoft.Getstarted | Remove-AppxPackage
</p>

<p>
<b>Groove App:</b> Get-AppxPackage -allusers Microsoft.ZuneMusic | Remove-AppxPackage
</p>

<p>
<b>Mail App:</b> Get-AppxPackage -allusers microsoft.windowscommunicationsapps | Remove-AppxPackage
</p>

<p>
<b>Maps App:</b> Get-AppxPackage -allusers Microsoft.WindowsMaps | Remove-AppxPackage
</p>

<p>
<b>Messaging App:</b> Get-AppxPackage -allusers Microsoft.Messaging | Remove-AppxPackage
</p>

<p>
<b>Mixed Reality App:</b> Get-AppxPackage -allusers Microsoft.MixedReality.Portal | Remove-AppxPackage
</p>

<p>
<b>Mobile Plans App:</b> Get-AppxPackage -allusers  Microsoft.OneConnect | Remove-AppxPackage
</p>

<p>
<b>Movies App:</b> Get-AppxPackage -allusers Microsoft.ZuneVideo | Remove-AppxPackage
</p>

<p>
<b>News App:</b> Get-AppxPackage -allusers  Microsoft.BingNews | Remove-AppxPackage
</p>

<p>
<b>Office Hub App:</b> Get-AppxPackage -allusers  Microsoft.MicrosoftOfficeHub | Remove-AppxPackage
</p>

<p>
<b>OneNote App:</b> Get-AppxPackage -allusers  Microsoft.Office.OneNote | Remove-AppxPackage
</p>

<p>
<b>Paint 3D App:</b> Get-AppxPackage -allusers  Microsoft.MSPaint | Remove-AppxPackage
</p>

<p>
<b>People App:</b> Get-AppxPackage -allusers  Microsoft.People | Remove-AppxPackage
</p>

<p>
<b>Phone App:</b> Get-AppxPackage -allusers  Microsoft.YourPhone | Remove-AppxPackage
</p>

<p>
<b>Photos App:</b> Get-AppxPackage -allusers Microsoft.Windows.Photos | Remove-AppxPackage
</p>

<p>
<b>Print 3D App:</b> Get-AppxPackage -allusers  Microsoft.Print3D | Remove-AppxPackage
</p>

<p>
<b>Skype App:</b> Get-AppxPackage -allusers  Microsoft.SkypeApp | Remove-AppxPackage
</p>

<p>
<b>Solitaire Collection App:</b> Get-AppxPackage -allusers  Microsoft.MicrosoftSolitaireCollection | 
Remove-AppxPackage
</p>

<p>
<b>Sticky Notes App:</b> Get-AppxPackage -allusers Microsoft.MicrosoftStickyNotes | Remove-AppxPackage
</p>

<p>
<b>Store App:</b> Get-AppxPackage -allusers Microsoft.WindowsStore | Remove-AppxPackage
</p>

<p>
<b>3D Viewer App:</b> Get-AppxPackage -allusers Microsoft.Microsoft3DViewer | Remove-AppxPackage
</p>

<p>
<b>Voice Recorder App:</b> Get-AppxPackage -allusers  Microsoft.WindowsSoundRecorder | Remove-AppxPackage
</p>

<p>
<b>Weather App:</b> Get-AppxPackage -allusers  Microsoft.BingWeather | Remove-AppxPackage
</p>
</div>
<br>
After running those commands apps that you couldn't uninstall before should be gone. But if you wish to bring them back use the command from the formula down below.

<div style="background: #70707070; border-radius: 5px; padding: 10px;">
<p>
Get-AppxPackage -allusers  <b>App name from uninstall command</b> | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppXManifest.xml"}
</p>
</div>
<br>

~ <a href="https://github.com/rara64">rara64</a>

<div id="disqus_thread"></div>
<script>
      (function() {
      var d = document, s = d.createElement('script');
      s.src = 'https://optimizer10.disqus.com/embed.js';
      s.setAttribute('data-timestamp', +new Date());
      (d.head || d.body).appendChild(s);
      })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>

