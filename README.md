# SmartisanOS_Build_Release

----

* Smartisan-SDK_sample-debug.apk 这个是根据SmartisanSDK 编译的一个demo程序。开发者可以通过这个APK来体验One Step的魅力。

* nexus6_shamu_mob31k.7z 这个是集成了One Step 和 Big Bang 功能的Nexus6的刷机包，可以用这个刷Nexus6的手机，体验One Step 和 Big Bang。[下载地址](http://dl2.smartisan.cn/shuaji/other_phone/opensource/nexus6_shamu_mob31k.7z) [刷机教程](https://developers.google.com/android/images#Flashing instructions)


###考虑到中国开发者得翻墙才能看刷机教程，特粘贴在下面
<h2 id="instructions">Flashing instructions</h2>
<p>The factory image downloaded from this page includes scripts that flashes the
device, typically named <code>flash-all.sh</code> (On Windows systems, use <code>flash-all.bat</code>
instead).</p>
<p>To flash a device using one of the system images below (or one of your own), you
need the latest <code>fastboot</code> tool. You can get it from one of the sources below.</p>
<ul>
<li>From a compiled version of the
  <a href="https://source.android.com/">Android Open Source Project</a>.</li>
<li>From the <code>platform-tools/</code> directory in the
  <a href="https://developer.android.com/sdk">Android SDK</a>. Be sure that you have the
  latest version of the <strong>Android SDK Platform-tools</strong> from the
  <a href="http://developer.android.com/tools/help/sdk-manager.html">SDK Manager</a>.</li>
</ul>
<p>Once you have the <code>fastboot</code> tool, add it to your <code>PATH</code> environment variable
(the <code>flash-all</code> script below must be able to find it). Also be certain that
you've set up USB access for your device, as described in the
<a href="http://developer.android.com/tools/device.html">Using Hardware Devices</a> guide.</p>
<aside class="caution"><strong>Caution:</strong><span> Flashing a new system image deletes all user data. Be certain to first
backup any personal data such as photos.</span></aside>
<p><strong>To flash a system image:</strong></p>
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
<p>Once the script finishes, your device reboots. You should now lock the
bootloader for security:</p>
<ol>
<li>
<p>Start the device in fastboot mode again, as described above.</p>
</li>
<li>
<p>Execute:</p>
<pre class="prettyprint notranslate" translate="no"><code>fastboot flashing lock
</code></pre>
<p>or, for older devices, run:</p>
<pre class="prettyprint notranslate" translate="no"><code>fastboot oem lock
</code></pre>
</li>
</ol>
<p>Locking bootloader will wipe the data on some devices. After locking the
bootloader, if you want to flash the device again, you must run <code>fastboot oem
unlock</code> again, which will wipe the data.</p>
