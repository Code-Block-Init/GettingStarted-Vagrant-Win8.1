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
<code>$cd "/d/[someother path]" </code><br>
<code>$git clone https://github.com/SamyPesse/How-to-Make-a-Computer-Operating-System.git </code><br>
The <code>src</code> folder consists of <code>kernel</code>, <code>disk-booting</code> and <code>user area</code>.<br>
Copy all files in <code>src</code> folder and paste it in <code>basic-os</code> directory. <br>
<b>Step 6:</b><br>
<code>$vagrant ssh</code><br>
<code>~$cd /vagrant </code><br>
<code>~$make all</code><br>
<code>~$make run</code> -- it can't run because the <code>disk-image file</code> in <code>basic-os/sdk</code> is corrupted.
<br>
<b>Step 7:</b><br>
Guess what? We successfully learnt <code>how an operating system is made and built</code>... <br>
Keep that <code>cloned-repo</code>. 
<br>
In that <code>cloned-repo</code> itself, the chapters will help in understanding the <code>internal-build</code>. <br>
Now, delete those basic-os directory files (except <code>Vagrantfile</code> and <code>.vagrant folder</code>) <br>
Keep <code>lucid32</code> for future use... <br>
<b>LOL</b><br>
<code>$vagrant halt</code><br>
<code>$vagrant up</code><br>
<code>$vagrant provision</code><br>
<br>
<b>Adding Try-Attempts:- </b> <br>
After <code>Step 5</code>, <br>
Goto <code>basic-os/sdk</code> directory, Delete the <code>c disk image, diskimage.sh, qemu.sh</code><br>
Create own disk image inorder to avoid file corruption. <br>
Make sure that <code>Git bash</code> is running in <code>admin mode</code>.<br>
<code>$vagrant ssh</code><br>
<code>~$cd /vagrant</code><br>
We will create disk-image inside <code>sdk</code> directory. <br>
<code>~$cd sdk</code><br>
<code>~$qemu-img create c.img 2M</code><br>
<code>~$fdisk ./c.img  << EOF</code><br>
<code>x</code><br>
<code>c</code><br>
<code>4</code><br>
<code>h</code><br>
<code>16</code><br>
<code>s</code><br>
<code>63</code><br>
<code>r</code><br>
<code>n</code><br>
<code>p</code><br>
<code>1</code><br>
<code>1</code><br>
<code>4</code><br>
<code>a</code><br>
<code>1</code><br>
<code>w</code><br> <br>
<code>~$fdisk -l -u ./c.img</code><br>
<br>
<code>~$losetup -o 32256 /dev/loop1 ./c.img</code> --- Got Permission denied <br>
<code>~$mke2fs /dev/loop1</code> --- Got Permission denied <br>
<code>~$mount  /dev/loop1 /mnt/ </code> --- Got Permission denied <br>
<code>~$cp -R bootdisk/* /mnt/ </code> --- Got Permission denied <br>
<code>~$umount /mnt/ </code> --- Got Permission denied <br>
If permission does not get denied, then a successfully disk image will be ready to run. <br>
<b>Installing <code>GRUB</code> on the disk:</b><br>
<code>~$grub --device-map=/dev/null << EOF </code><br>
<code>>>device (hd0) ./c.img</code><br>
<code>>>geometry (hd0) 4 16 63</code><br>
<code>>>root (hd0,0)</code><br>
<code>>>setup (hd0)</code><br>
<code>>>quit</code><br>
<code>>>EOF</code><br>
<br>
<code>~$losetup -d /dev/loop1</code> --- Got Permission denied <br>
If permission is not denied, then GRUB will successfully boot. <br><br>
<code>~$make run</code><br>
The OS will run if it never received permission-denied in any commands. <br>
<br>
<code>~$exit</code><br>
<code>$vagrant halt</code><br><br>
If failed, Go to <code>Step 7</code>.
