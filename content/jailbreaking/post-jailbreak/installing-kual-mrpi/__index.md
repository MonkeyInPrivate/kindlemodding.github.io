---
layout: default
parent: Post Jailbreak
title: Installing KUAL & MRPI
weight: 2
slug: index
---

# Installing KUAL and MRPI
You will need to install KUAL (Kindle Unified Application Launcher) and MRPI (MobileRead Package Installer) to run homebrew on your Kindle.

<div id="guide">
    <div class="buttons">
        <button id="prev">Previous Step</button>
        <span id="stepCounter"></span>
        <button id="next">Next Step</button>
    </div>
    <div id="stepwrapper" class="stepwrapper">
        <div class="step">
            <h2>Download the correct KUAL version</h2>
            <div class="stepContent">
                <table>
                <thead>
                    <tr>
                        <th>Device Generation</th>
                        <th>Instructions</th>
                        <th>KUAL Download</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>K5 and newer</td>
                        <td>Download and continue to next steps</td>
                        <td><a href="./Update_KUALBooklet_HDRepack.bin">Update_KUALBooklet_HDRepack.bin</a></td>
                    </tr>
                    <tr>
                        <td>K4 and older</td>
                        <td>Download, place in documents folder and move onto <a href="../koreader.html">Installing KOReader</a></td>
                        <td><a href="./KUAL-KDK-1.0.azw2">KUAL-KDK-1.0.azw2</a></td>
                    </tr>
                    <tr>
                        <td>If none of the above methods work</td>
                        <td>Follow the instructions on the repository and then move onto <a href="../disable-ota.html">Disabling OTA Updates</a></td>
                        <td><a href="https://github.com/KindleTweaks/PEKI">https://github.com/KindleTweaks/PEKI</a></td>
                    </tr>
                </tbody>
                </table>
            </div>
        </div>
        <div class="step">
            <h2>Download MRPI</h2>
            <div class="stepContent">
                <a class="button" href="./kual-mrinstaller-khf.zip">MRPI (for modern devices)</a>
                <p>This version of MRPI is provided by <a href="https://fw.notmarek.com/khf/">Marek</a></p>
                <a class="button" href="./kual-mrinstaller-1.7.N-r19303.zip">MRPI (for legacy devices - pre-K5)</a>
                <p class="important">You may need to free up 220 MB of space to install both MRPI and KUAL <a href="#troubleshooting">without issues</a></p>
                <p class="warning"><b>Make sure Airplane mode is on before freeing up this space.</b> If it isn't, your Kindle may use the freed space to download and install an OTA update.</p>
            </div>
        </div>
        <div class="step">
            <h2>Extracting MRPI</h2>
            <div class="stepContent">
            <p>Extract the contents of the MRPI tar file you downloaded, and copy the <code>extensions</code> and <code>mrpackages</code> folders to your Kindle</p>
            <br/>
            <img src="./mrpackages_extensions_folders.png" />
            </div>
        </div>
        <div class="step">
            <h2>Extracting/Copying KUAL</h2>
            <div class="stepContent">
            <p class="note">If your device is older than the K5 (Kindle Touch), you only need to copy the <code>KUAL-KDK-1.0.azw2</code> file to your Kindle's <code>documents</code> folder, you can skip the next steps</p>
            <p class="note">If your device is the K3 (Kindle Keyboard) or older, you should instead use the <code>KUAL-KDK-1.0.azw</code> file and copy it to your Kindle's <code>documents</code> folder, you can skip the remaining steps</p>
            <p class="important">If you downloaded KUAL for <strong>legacy devices</strong>, extract the .tar.xz to get the <code>Update_KUALBooklet_*_install.bin</code> file</p>
            <p>Copy the <code>Update_KUALBooklet_HDRepack.bin</code> file (if you chose KUAL Coplate for Kindles newer than the K5) or the <code>Update_KUALBooklet_*_install.bin</code> file (for legacy devices) to your Kindle's <code>mrpackages</code> folder</p>
                <br/>
                <img src="./kual_install_bin.png" />
            </div>
        </div>
        <div class="step">
            <h2>Eject and unplug your Kindle</h2>
            <div class="stepContent">
                <img src="./eject.png" />
            </div>
        </div>
        <div class="step">
            <h2>Running MRPI</h2>
            <div class="stepContent">
                <p>On your Kindle, type <code>;log mrpi</code> into the search bar and hit enter</p>
                <br/>
                <img src="./run_dispatch.png" />
            </div>
        </div>
        <div class="step">
            <h2>Done</h2>
            <div class="stepContent">
                <p>Now wait whilst KUAL is installed, your Kindle screen turns white and shows some icons, after a while you will be returned to your library and see a <code>KUAL</code> book appear in it.</p>
                <p class="highlight">If you see a "Application Error" dialog, you can close it without worry - this is normal behaviour on some modern Kindles</p>
                <br/>
                <img src="./success.png" />
                <p>If you face any issues, please read the <a href="#troubleshooting">troubleshooting</a> section.</p>
            </div>
        </div>    
    </div>
    <div class="buttons">
        <button id="prev">Previous Step</button>
        <span id="stepCounter"></span>
        <button id="next">Next Step</button>
    </div>
</div>
<script>new Guide("guide", "../disable-ota.html", "Disabling OTA Updates");</script>

## Troubleshooting

- The installation or functionality of **KUAL** and **MRPI** may fail if there is not enough free space on your Kindle. If you are using the "[fill storage](../../prevent-auto-update/)" method to block updates, make sure your Kindle has `150 MB` of available space before installing KUAL and MRPI
- Verify that all folders and files are in the correct locations on your Kindle.
- Try restarting the Kindle if the `;log mrpi` command is not responding
- Ensure that the file does not have any special characters such as brackets in it, some browsers may rename files adding `(1)` or other additional suffixes to the file name and these should be removed before copying to the Kindle
