Few weeks back, someone mailed me asking me to check their company product and asked me to give feedback. <br>
So, i geek-ed into their website and found something called <a href="http://en.wikipedia.org/wiki/Vagrant_%28software%29">"vagrant"</a>.
<br>
While reading about it in curiosity, i found it cool. It's built in Ruby. So, i decided to play with it. <br> <br>
Here are some of the following steps to get started with <code>Windows 8.1</code>:- <br>
Note: None of the steps works in offline. Make sure to turn on the Internet ;) <br>
<b>Step 1:</b> Install <a href="https://www.virtualbox.org/wiki/Downloads">VirtualBox</a>.<br>
<b>Step 2:</b> Install <a href="https://www.vagrantup.com/downloads.html">Vagrant</a>.<br>
Note:- If you are <code>Windows 10 user</code>, then make sure to test it in another system which already has Windows10.<br>
After successfully installing Vagrant in Windows10, then I'd to restart my system for booting. <br>
Then... BAM! Windows10 collapsed and died. So, this is a warning.<br>
<b>Step 3:</b> Install <a href="http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe">PuTTY</a>.<br>
<b>Step 4:</b> Install <a href="http://the.earth.li/~sgtatham/putty/latest/x86/puttygen.exe">PuTTYgen</a>.<br>
Good job! Now, we will require <code>Cloud</code>. <br>
<b>Step 5:</b> Open Command Prompt (run as admin). Dive-in to the directory location.<br>
If your files in another disk, then type <code>cd\</code> and followed by <code>d:</code> or <code>e:</code> or whatever. <br>
Remember to remove the <code>Vagrant file</code> which will be found in <code>bin</code> folder. <br>

<b>Step 6:</b>
<code>vagrant init ubuntu/trusty64</code> --- this is official box for Ubuntu Server 14.04 LTS. <br>

<b>Step 7:</b>
<code>vagrant up</code> <br> --- Now, we need to wait for few hours for the installation to complete.
