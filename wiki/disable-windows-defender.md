---
layout: page
title: Disable Windows Defender
description: How to disable Microsoft Defender Antivirus and Antimalware Service Exucutable in Windows 10
---

<style>
  h1, h2, h3, h4, h5 ,h6 {
    color: rgba(255,255,255,0.8);
  }
</style>

*Method compatible with Windows 10 2004*

<img src="/wiki/images/disable-windows-defender-1.png"/>

***Microsoft Defender aka Windows Defender*** is a built-in Antivirus in Windows 10. Although having protection is important if you are running slower hardware it may cause a lot of performance issues, especially when we are talking about Windows Defender. If you find yourself with ***"Antimalware Service Executable"*** process taking over your PC by high CPU and Disk usage it might be time to consider disabling Microsoft Defender entirely. The process of disabling it is a little bit tricky but the award exceeds the effort.

First of all, you should download an app that lets you run command line with TrustedInstaller permissions which is crucial when trying to disable Windows Defender on a deeper level.
For that you can use <a href="https://github.com/rara64/GetTrustedInstaller/releases/">my fork of GetSystem called GetTrustedInstaller</a> but feel free to use another software should you want to.

<img src="/wiki/images/disable-windows-defender-2.gif"/>

After downloading <a href="https://github.com/rara64/GetTrustedInstaller/releases/">GetTrustedInstaller executable</a> and extracting it from the zip with all the other extra files we are ready for the ride! So, first head to Defender settings. To do that open search from the taskbar and type the phrase ***"Windows Security"*** and click on the result to go into settings. 

Now in the Windows Security window head to the ***Virus & threat protection***. Under ***Virus & threat protection settings*** hit Manage settings. We will need to act fast because protection reactivates itself after some time. So let's get ready for the next step before we touch anything in this window.

<p class="message">
<b>Warning:</b> If you are using another software to run commands as TrustedInstaller this might be different for you
</p>

<img src="/wiki/images/disable-windows-defender-3.gif"/>

Once again open search from the taskbar and type ***"cmd.exe"***, then run the result. First, we need to go to the location where we have GetTrustedInstaller executable. To do that type the letter of the drive where it's stored like this:

`C:`

Then we need to provide an absolute path to the folder where GetTrustedInstaller executable is. To do that type:

`cd C:\Users\PC\Downloads\x64`

**Please edit this command to match your path and disk letter.**

Now we are going to write:

`GetTrustedInstaller.exe "C:\Windows\System32\cmd.exe"`

You should see a new cmd.exe window pop-up.

So, we are ready to go back into Defender settings and disable all the options: ***Real-time protection, Cloud-delivered protection, Automatic sample submission, and the most important one Tamper Protection.*** After that quickly head to the cmd.exe window that we opened with GetTrustedInstaler and type:

`sc stop WinDefend`

By doing this we stoped the Windows Defender service, now we are going to make it so that it won't start on its own. To do that type:

`sc config WinDefend start= disabled`

If everything went ok you can close all of the windows that we opened.

<img src="/wiki/images/disable-windows-defender-4.gif"/>

The only thing left now is to disable Windows Defender icon that shows up on the taskbar and disable annoying notifications informing you that Defender is not running. For the first one, head to the Task manager which you can bring with a simple shortcut, just hit ***Ctrl + Shift + Esc*** on your keyboard. In the task manager ***click on Startup and locate Windows Security notification icon.*** When you find it click on it with the right mouse button and hit disable.

The last thing left to do is to disable Defender notifications. For that open search and type ***"regedit"***. Be careful when dealing with the registry editor - don't touch keys that we are not interested in. Ok, so in this window head to ***HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender Security Center\Notifications***. If this path doesn't fully exists create needed keys by right-clicking on the parent folder and choosing ***New > Key***. Now modify or create from the right-click menu a ***DWORD 32-Bit value*** called ***"DisableNotifications"***. Set its value data to 1. Now, we can close the registry editor window.

After the restart, you should be met with a disabled Windows Defender Antivirus with Antimalware Service Executable no longer running in the background :)

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