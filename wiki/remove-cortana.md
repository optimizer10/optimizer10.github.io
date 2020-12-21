---
layout: page
title: Remove Cortana
description: How to remove Cortana in Windows 10
---

<style>
  h1, h2, h3, h4, h5 ,h6 {
    color: rgba(255,255,255,0.8);
  }
</style>

*Method compatible with Windows 10 2004*




<img src="/wiki/images/remove-cortana-1.png"/>

***Cortana*** is a virtual assistant which is included with every Windows 10 installation. Although assistance from Cortana might be helpful not everyone wants to use Cortana on their PC. Thankfully, it's not that hard to disable it.

<img src="/wiki/images/remove-cortana-2.gif"/>

First, open search from the taskbar and type the phrase ***"powershell"***. Click on the result with the right mouse button and from the pop-up menu select ***Run as administrator***. Now we are going to execute the command below:

`Get-AppxPackage -allusers Microsoft.549981C3F5F10 | Remove-AppxPackage`
This command will remove Cortana app for all users.


Should you want to get Cortana back, please execute the following command:
`Get-AppxPackage -allusers Microsoft.549981C3F5F10 | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppXManifest.xml"}`

If you want to get rid of the Cortana icon on the taskbar, click the right mouse button on the empty part of the taskbar and click ***Show Cortana Button***.
After doing this Cortana button should be no longer on your taskbar.

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





