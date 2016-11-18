### Getting Started

To get started , you'll need to get familiar with
* [Build Environment](http://source.android.com/source/initializing.html)
* [Git and Repo](http://source.android.com/source/using-repo.html)
* [Preparing to Build](http://source.android.com/source/building.html)

To initialize your local repository using a command like this:

***For Smartisan Internal Developer***
```sh
    repo init -u https://github.com/SmartisanTech/android.git -b smartisan-m -m manifest_smartisan_internal.xml --repo-url smartisan:/googlesource/git-repo
```
***For Other Developer***
```sh
    repo init -u https://github.com/SmartisanTech/android.git -b smartisan-m -m manifest.xml
```
Then to sync up:
```sh
    repo sync -cdj4
```

### To flash a system image:
<aside class="caution"><strong>Caution:</strong><span> Flashing a new system image deletes all user data. Be certain to first
backup any personal data such as photos.</span></aside>
<ol>
<li>
<p>Download the appropriate system image for your device below, then unzip it
   to a safe directory.</p>
</li>
<li>
<p>Connect your device to your computer over USB.</p>
</li>
<li>
<p>Start the device in fastboot mode with one of the following methods:</p>
<ul>
<li>
<p>Using the <a href="http://developer.android.com/tools/help/adb.html">adb tool</a>:
  With the device powered on, execute:</p>
<p>adb reboot bootloader</p>
</li>
<li>
<p>Using a key combo: Turn the device off, then turn it on and immediately
  hold down the relevant
  <a href="https://source.android.com/source/building-devices.html#booting-into-fastboot-mode">key combination</a>
  for your device. For example, to put a Nexus 5 ("hammerhead") into
  fastboot mode, press and hold Volume Up + Volume Down + Power as the
  device begins booting up.</p>
</li>
</ul>
</li>
<li>
<p>If necessary, unlock the device's bootloader by running:</p>
<pre class="prettyprint notranslate" translate="no"><code>fastboot flashing unlock
</code></pre>
<p>or, for older devices, run:</p>
<pre class="prettyprint notranslate" translate="no"><code>fastboot oem unlock
</code></pre>
<p>The target device will show you a confirmation screen. (This erases all data
on the target device.)</p>
</li>
<li>
<p>Open a terminal and navigate to the unzipped system image directory.</p>
</li>
<li>
<p>Execute the <code>flash-all</code> script. This script installs the necessary
   bootloader, baseband firmware(s), and operating system.</p>
</li>
</ol>
