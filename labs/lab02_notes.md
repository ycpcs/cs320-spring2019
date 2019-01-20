---
layout: default
title: "Notes for Lab 2: Guessing Game WebApp"
---

Determining the JRE System Library
===============

These instructions are for **Eclipse Oxygen** (which is installed on the PCs in KEC 119 and KEC 123).  The instructions will be similar for other versions of Eclipse - but there might be some slight differences.

All of the labs have been reconfigured to use **JRE System Library[JavaSE-1.8]**, which is installed on the PC's in both KEC 119 and KEC 123.  It is possible that the configuration you are using on your own PC, or even on a lab PC could vary such that no suitable version of Java JRE 1.8 can be found.  The instructions below will help you establish the proper JRE System Libraries for the labs for CS320.

If you are using an older version of the **JRE System Library**, you might need to change the default **JRE System Library** version to a later version in order to get **CS320\_Lab02** to work.  A **JRE System Library** version of **jre1.8.0\_51** or later should work fine - choose the latest version available.

In KEC 119 and KEC 123, the latest version of the **JRE System Library** is **1.8.0\_181**.

* Create a folder on your home drive **(H:)** named **cs320-spring2019**.

* Set the default workspace for Eclipse to that location.

* Download **CS320\_Jetty9.zip** and **CS320\_Lab02.zip**.

* Open Eclipse, switch the **Workspace** to **H:/cs320-spring2019**.

* Import **CS320\_Jetty9.zip**.

* Import **CS320\_Lab02.zip**.

* Expand the **CS320_Lab02** project.

* If it shows the **JRE System Library** either as **JRE System Library[JavaSE-1.8]** or **jdk1.8.0\_51** or later, then you likely have no further steps to take.

Changing the JRE System Library
=========

On the other hand, if the **JRE System Library** is shown as "unbound", you will likely need to switch to a compatible library.

Go to **C:/Program Files/Java** and look for a JDK folder labelled **jdk1.8.0\_xxx**.  Hopefully, you have one of those installed in the Java folder.  For the lab PCs, there could be multiple versions installed - choose the latest version.  If a compatible version is present, then do the following:

* Go into Eclipse, right-click on the **CS320\_Lab02** project.

* Go to the the bottom, select **Properties**.

* Select **Java Build Path** on the left.

* Select the **Libraries** tab.

* Select the **JRE System Library** entry.

* Select the **Edit...** button on the right.

* Select the **Installed JREs...** button on the right.

* That will pop up a list of installed JRE's.

* If you see one for **jdk1.8.0\_51** (or later), select whichever one you want, and hit **Apply**, followed by **OK**.

* You should now see that the **Workspace default JRE** has changed to the one you just selected.

* Hit **Finish**, and then **OK**, and you are ready to roll.  The **JRE System Library** for **CS320\_Lab02** should also have been updated.

* If you do not see an acceptable JDK version, then  select **search**, and browse to the **C:/Program File/Java** folder under **Computer**, and hit **OK**.

* Now, all of the currently installed JDKs and JREs that are included in that folder will show up, and you can select an appropriate one. (**Apply**, **OK**, **Finish**, **OK**).

* You should now be able to run the lab.

Installing a new JDK from Oracle
=========

If you do not find an acceptable JDK installed on your computer, you'll have to install one from this location:

[Oracle Java SE 8 Downloads](http://www.oracle.com/technetwork/java/javase/downloads/java-archive-javase8-2177648.html)

Create a free Oracle account and then download and install the appropriate version for your Eclipse/java installation - the 64-bit version will show up in **C:/Program Files/Java**, and then you can select it as described above.

* Select **Java SE Development Kit 8u91** or later - select the latest one available.

* Now select the appropriate file to download - you want the SDK.  For Windows 64-bit, that will be **jdk-8591-windows-x64.exe** or **later**.

* Download the file - it is 180MB, it could take a while to download.

* Run the executable - it will bring up the installer.  By default, it will install to the **C:/Program Files/Java** folder.  It will install both the JDK and the JRE at that location.

* After it is installed, you can then follow the above instructions to set the **JRE System Library** to the JDK you just installed.


Other Issues
=========
There are some other issues that have been popping up with **CS320\_Lab02**.

* For some unknown reason, the **CS320\_Lab02.zip** file might be protected, and Eclipse won't let you import it.  Let me know if this continues to happen - I think this is fixed with the latest ZIP file.

* When you start Eclipse on the lab PCs, Windows will likely warn you about running a program that was downloaded from the Internet.  You can ignore this and move on.

* When you go to run **main()** in the **CS320\_Lab02** project, you may get a Windows Firewall warning.  You can hit **Cancel** and the lab will work.