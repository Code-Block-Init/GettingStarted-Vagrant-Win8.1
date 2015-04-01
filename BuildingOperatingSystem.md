<b> Getting Started on Building an Operating System using Vagrant </b>
(added <a href="https://github.com/SamyPesse/How-to-Make-a-Computer-Operating-System">credits</a>)<br><br>
<b>Step 1:</b><br>
If you don't have vagrant installed, 
then follow first 10 steps in 
<a href="https://github.com/dragonwolverines/GettingStarted-Vagrant-Win8.1/blob/master/README.md">README</a>.<br>
<b>Step 2:</b><br>
Using Git... <br>
<code>$cd "/d/vagrant" </code> <br>
<code>$mkdir basic-os && cd basic-os </code><br>
<code>$vagrant box add lucid32 http://files.vagrantup.com/lucid32.box </code> --- this is Ubuntu lucid32 image
<br>
It will take some hours to complete the installation... <br>
<b>Step 3:</b><br>
After installation... <br>
Open any code editor... <br>
Copy-Paste <a href="https://github.com/ashumeow/How-to-Make-a-Computer-Operating-System/blob/master/src/Vagrantfile">this file</a> into the editor and save it as <code>Vagrantfile</code> without any file extension in <code>basic-os</code> directory.
<br>
<b>Step 4:</b><br>
<code>$vagrant up</code><br>
It will take some minutes to complete (since it's first time to boot up lucid32)...<br>
<b>Step 5:</b><br>
<code>$vagrant ssh</code><br>
