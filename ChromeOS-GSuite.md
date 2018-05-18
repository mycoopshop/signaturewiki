The Chromium developer how-tos and Group Policy presentations outline all of these:

 * [Chrome Group Policy](http://www.scribd.com/doc/163766676)
 * [Getting Around the Chromium Source Code Directory Structure](http://www.chromium.org/developers/how-tos/getting-around-the-chrome-source-code)
 * [Chrome Windows Build](https://chromium.googlesource.com/chromium/reference_builds/chrome_win/+/master)
 * [Troublesome DLLS](https://code.google.com/p/chromium/codesearch#chromium/src/content/common/sandbox_win.cc&q=ktroublesome&sq=package:chromium&type=cs&l=43)
 * [Inappropriate DLL load addresses](https://code.google.com/p/chromium/issues/detail?id=321626)
* https://www.chromium.org/chromium-os/developer-guide/using-sdk-standalone
* https://www.chromium.org/chromium-os/developing-apps-on-your-chromium-os-device

Here's a partial rundown:

<pre>

:: All Chrome processes.
chrome.exe      	
icudt.dll               

:: Browser processes only.
chrome.dll            

:: Renderer processes.
ffmpegsumo.dll

:: GPU process only.
libegl.dll
libglesv2.dll
d3dcompiler_43.dll  
d3dcompiler_46.dll  

:: PLugins.
ppgooglenaclpluginchrome.dll

:: Chrome frame.
chrome_frame_helper.dll
npchrome_frame.dll
</pre>


* https://dev.chromium.org/chromium-os/developer-information-for-chrome-os-devices/workaround-for-battery-discharge-in-dev-mode
* https://www.chromium.org/developers/telemetry/running-telemetry-on-chrome-os
* https://www.chromium.org/chromium-os/tips-and-tricks-for-chromium-os-developers
* https://www.chromium.org/chromium-os/tips-and-tricks-for-chromium-os-developers
* https://www.chromium.org/chromium-os/developer-guide/chromium-os-sandboxing
* https://www.chromium.org/chromium-os/chromiumos-design-docs/recovery-mode
* https://www.chromium.org/chromium-os/chromiumos-design-docs/network-portal-detection
* https://support.google.com/chromebook/answer/1080595
* https://support.google.com/chromebook/answer/183101?hl=en
* https://support.google.com/chromebook/answer/6250945?hl=en
* http://www.scentral.k12.in.us/technology/2096-chromebook-q-a-s/file
* https://www.technibble.com/how-to-gain-computer-repair-customers-through-volunteer-work/
* http://towncountrynews.com/2017/06/05/hands-on-learning-milaca-man-teaches-braham-students-to-repair-school-issued-devices/
* http://www.pocketables.com/2013/03/how-to-use-change-the-dns-settings-on-your-chromebook-and-use-googles.html
* https://support.opendns.com/hc/en-us/articles/228006847-Configuration-for-Chromebook-OS
* https://github.com/dnschneid/crouton/wiki/How-to-mount-network-shares-on-Chromebook-(sshfs,-cifs,-nfs-etc)
* https://qualityshepherd.com/2013/02/chromebook-advanced-shell-commands/
* https://www.quora.com/How-is-Chrome-OS-built-on-top-of-Linux
* https://www.bettercloud.com/monitor/the-academy/15-free-google-apps-training-sessions/
* https://turbofuture.com/internet/How-to-Host-a-Podcast-on-Blogger
* https://hubpages.com/business/How-to-Create-a-Strong-RSS-Feed-for-Facebook-or-Twitter
* https://gsuiteupdates.googleblog.com
* https://v8project.blogspot.com
https://stackoverflow.com/questions/46452365/how-can-i-get-system-uptime-programmatically-on-the-chrome-os-platform
https://developer.chrome.com/native-client/migration
https://code.visualstudio.com/docs/languages/csharp
https://groups.google.com/forum/#!forum/crouton-central
https://blog.lessonslearned.org/building-a-more-secure-development-chromebook/
https://www.asp.net/get-started
http://techintranslation.com/git-python-and-node-on-a-toshiba-chromebook-without-crouton-or-linux/
https://medium.com/@dihuta/install-nodejs-on-chromebook-c17677874d81
https://andropenoffice.blogspot.com/search/label/HOWTO