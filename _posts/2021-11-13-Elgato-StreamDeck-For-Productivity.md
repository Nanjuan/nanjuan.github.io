---
layout: post
title:  "Elgato Stream Deck for Pentesters"
categories: [Productivity, Tutorial]
authorMain: Nestor N Torres
tag: Stream Deck
description: I made this page to show how I use the Elgato Stream Deck for pentesting. Hopefully, this page and the instructions here motivate you to get a stream deck and use it for pentesting and every day productivity. 
---
 
<a id="Top"></a> 
### Contact
- [LinkedIn](https://www.linkedin.com/in/nanjuan/)
- Email: nestor@nntorres.com

### Table
1. [Summary](#Summary)
2. [Prerequisites](#preinfo)
3. [Open Chrome with Different Profiles](#OpenChrome)
4. [How to Metasploit to Stream Deck](#metasploit)
5. [How to open Burp and other tools](#openTools)
6. [Add Automation Script to Stream Deck](#Add2StreamDeck)

## Summary <a id="Summary"></a> 
Why should I use a Stream Deck to be more productive? 

One day, I came up with this idea while looking at random tech online and came across the Elgato Stream Deck. Streamers use the Stream Deck to make repetitive actions like turning the mic on and off to record a clip while they stream easily. I realized that I could simply use automation and invoke these scripts from the stream deck to increase my productivity and automate mundane actions like opening different chromes pages from different profiles. I also plan to use this document as a live document where I can keep adding automation scripts I add to my Stream Deck. 

[Top](#Top)

## Prerequisites <a id="preinfo"></a>
Some prerequisites to keep in mind if you planning to follow this tutorial. I am using Mac OS 11.6 at the time of writing this tutorial. For Chrome, I am using the laters version in November 2021. Also, I am using Mac OS Automator software. Also, if I see a lot of interest in this post, I might work on Windows version for this tutorial. 

[Top](#Top)

<a id="OpenChrome"></a>

## How to open Chrome with different Profiles/Accounts on the Stream Deck.

The following step will help you create the necessary Automator scripts to open different chrome windows with other accounts from your computer. 

1. Open the `Automator` program and click `New Document` if prompt. Then select application and click choose. 
![Section1](/blog-assets/Elgato-StreamDeck-For-Productivity/Automation-App-Open-Click-App.png)

2. Search on the left upper search bar for `Run Shell Script` and drag that actions to the right window. 
![Section1](/blog-assets/Elgato-StreamDeck-For-Productivity/Automation-Run-Shell-Script-on-Right.png)

3. On the Run Shell Script windows, enter the following command line. This line will open Chrome and with the profile set as one in a new chrome window. By increasing the number and pressing `Run` on the Automator top right corner, you can test the code to verify you are able to open the correct browser profile you are trying to add for automation. 
    ```
    /Applications/Google\ Chrome.app/Contents/MacOS/Google\ chrome --profile-directory="Profile 1"
    ```

    ![Section1](/blog-assets/Elgato-StreamDeck-For-Productivity/Automation-Run-Script-Command-Line.png)

4. After you are able to test and run the correct profile got to `File` and click `save`. On the windows that open, name the Automation program as you which and make sure the File Format is set to `Application` and click save. 
![Section1](/blog-assets/Elgato-StreamDeck-For-Productivity/Automation-Save-Window.png)

5. To test the script, just find where it is saved and click it like any other application to see if it opens Chrome with the correct profile. To choose a different profile, perform the same steps on the group, change the `Profile 1` to `Profile 2`, and keep increasing the number depending on how many profiles you have on your Chrome Browser. 
![Section1](/blog-assets/Elgato-StreamDeck-For-Productivity/Automation-Run-Script-Command-Line-2.png)

[Top](#Top)

<a id="metasploit"></a> 

## How to Add Metasploit to Elgato Stream Deck. 

The following steps will show you how to add Metasploit to Elgato Stream Deck.

* pre-requirement make sure you have Metasploit installed and you are able to run it from the command line. 

1. Open the Elgato Stream Deck software and search for `Multi Action` on the right search bar and drag to one of the empty fiels. 
![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-1.png)

2. Enter the name you desire on the title section and on Content click on Content section the little arrow icon. Then add the follwing step to the Multi Action. 
    1. System: Open
    2. System: Text
    3. Stream Deck: Delay
    4. System: Text
    5. Stream Deck: Delay
    6. System: Text

    ![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-2.png)

3. On the System: Option select the terminal application to open. 
![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-3.png)

4. On the first System: Text enter the title you want to use to identify this step then enter the command line to start the Metasploit databse my example is below and check the box that said. `Press Enter After messages`

    ```
    /opt/metasploit-framework/bin/msfdb start
    ```
![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-4.png)

5. On the two Stream Deck: Delay add `2000 ms` 
![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-5.png)

6. On the second System: Text enter the title you want to use to identify this step then enter the command line to answer the question from starting msfdb. 
![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-6.png)

7. On the last System: Text enter the title you want to use to identify this step then enter the command line to start msfconsole. `* Remember you will need to enter you password for sudo`

    ```
    sudo /opt/metasploit-framework/bin/msfconsole
    ```
    ![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-7.png)

8. I added another I con use to stop the msfdb after you are done with Metasploit. For this you will aldo need a `Multi Action` and add the fallowing functionality. 
    1. System: Open 
    2. System: Text
![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-8.png)

9. On the System: Option select the terminal application to open. 
![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-9.png)

10. On the first System: Text enter the title you want to use to identify this step then enter the command line to stop the database. 

    ```
    /opt/metasploit-framework/bin/msfdb stop
    ```
    ![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-10.png)

11. Last step change your icons to one you want if you want to use the icon I have you can save it from this post as png. 

    ![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-11-1.png)

    ![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-11-2.png)

    ![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/metasploit-Stream-Deck-11-3.png)
    
    * icon

    ![Section2](/blog-assets/Elgato-StreamDeck-For-Productivity/msfconsole.png)

[Top](#Top)

<a id="openTools"></a> 

## How to open Burp and other tools with Stream Deck

The following steps will show you how to add Burp and other software to Elgato Stream Deck.

1. Open the Elgato Stream Deck software and search for `Open` on the right search bar and drag to one of the empty fiels. 
![Section3](/blog-assets/Elgato-StreamDeck-For-Productivity/openApplications-1.png)

2. Click on the Icon on the middle windows and on the options bellow click on `Choose` then select the app you want to run with that click. 
![Section3](/blog-assets/Elgato-StreamDeck-For-Productivity/openApplications-2.png)

3. Last test the new icon and recreate any of the steps with as many apps as you want too add to the stream deck. 
![Section3](/blog-assets/Elgato-StreamDeck-For-Productivity/openApplications-3.png)

[Top](#Top)

<a id="Add2StreamDeck"></a>

## How to Add Automation script to Elgato Stream Deck.

The following steps will show you how to add Automator scripts to Elgato Stream Deck.

1. Open the Elgato Stream Deck software and search for `open` on the right search bar. 
    ![SectionLast](/blog-assets/Elgato-StreamDeck-For-Productivity/Stream-Deck-Software-Open.png)

    ![SectionLast](/blog-assets/Elgato-StreamDeck-For-Productivity/Stream-Deck-Software-Search-For-Open.png)

2. Drag the open icon on the Stream Deck software to an empty window. 
![SectionLast](/blog-assets/Elgato-StreamDeck-For-Productivity/Stream-Deck-Software-MoveOpen-To-Window.png)

3. Click on the icon on the middle window, enter your title, click `choose`, and select the application you want to run when clicking on the Stream Deck. 
![SectionLast](/blog-assets/Elgato-StreamDeck-For-Productivity/Stream-Deck-Software-Select-Application.png)

4. I recommend creating a folder with your Icons and logos you might want to use for the icon. Remember to try different sizes to get a good result on the Stream Deck. This is how I have my icons organized. Remember, the icon might not look fine, so you might need to try a different resolution on the Stream Deck to make it look correct. 

[Top](#Top)

#### Reference: 

https://winaero.com/run-google-chrome-with-different-profiles/
https://peter.sh/experiments/chromium-command-line-switches/


