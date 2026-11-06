# Module 2: Basic Switch and End-Device Configurations

[All modules](Cisco-1-Notes.md) · [Module 1](Module-1.md) · [Module 2](Module-2.md) · [Module 3](Module-3.md)

[Review questions](#review-questions) · [CLI shortcuts](#cli-shortcut-reference) · [Switch settings lab](#configure-initial-switch-settings) · [Slides](#presentation-slides)

## Review Questions

**A.1 Please explain the 3 different access methods you can use to connect to a switch's operating system.**

- Console - A physical management port to connect directly to the switch.
- Secure Shell - A secure connection to remotely establish a CLI connection, requires active network.
- Telnet - Unsecure remote connection to a CLI, requires active network, will broadcast usernames, passwords, etc in plain text.

**A.2 What's the difference between telnet and SSH? Which one would you choose to use and why?**

SSH is secure and encrypted where Telnet is not even remotely secure and will broadcast user info in plain text that anyone that is connected can see.

**A.3 Explain the 2 primary modes of operation in a networking device.**

- User exec mode - a view only mode that does not allow you to change the configuration of a device.
- Privileged exec mode - a more powerful mode that allows you to view and change all files.

**A.4 Explain what Global Configuration Mode is.**

Global configuration mode allows you to change any configuration on a router, including usernames, passwords, etc.

**A.5 When using a networking device's CLI, why is the "?" one of the most valuable keys on the keyboard?**

? will help you understand context-sensitive commands such as which commands are available, which commands start with specific characters, or which arguments and keywords are available.

**A.6 What Hot Keys and Shortcuts are available to you in a networking device's CLI?**

- I provided a screenshot of the hotkeys.
- There is also enter to display the next line, space bar to display the next screen, any other key will return to the previous prompt.
- Ctrl-C will return to privileged exec mode or aborts to the command prompt if you are in setup.
- Ctrl-Z will return to privileged exec mode.
- Ctrl-shift-6 will abort DNS lookups, traceroutes, pings, etc.

**A.7 Explain some guidelines to keep in mind when it comes to naming your networking devices.**

Names should start with a letter, contain no spaces, end with a letter or number, use only letters, numbers or dashes, and be less than 64 characters in length.

**A.8 In order to keep our devices secure we will be using passwords. What can we do to make our passwords as secure as possible?**

Use passwords that are more than eight characters in length, use upper and lowercase letters, numbers, special characters, or numeric sequences, avoid using the same password for all devices, and do not use common words that are easily guessed.

**A.9 What is the difference between a Privileged EXEC Password and a User Exec Password?**

A user exec password will be entered by using the password command and the privileged exec password will be used by entering the enable secret (password) command.

**A.10 What are a networking device's two main configuration files, and where are they stored?**

- Startup-config contains all commands that will be used by startup or reboot and is stored in NVRAM
- Running-config reflects the current configuration and is stored in RAM. It will lose all content once the device is powered down or restarted.

**A.11 Why does a device on a network need an IP Address?**

An IP address is basically the name that your device uses to communicate with other devices. It cannot communicate without one.

**A.12 How many IP Addresses can one device have at the same time?**

A device can have one IP address per network interface. For example Wi-Fi and Ethernet can have different IP addresses.

**A.13 What command allows you to verify a computer's IP Configurations on a Windows PC?**

`ipconfig`

**A.14 What is the name of the interface on a switch that gets an IP Address? Also, how do you put an IP Address on that interface?**

Assign the management IP address to a switched virtual interface (SVI).

```text
configure terminal
interface vlan 1
ip address <ip-address> <subnet-mask>
no shutdown
end
copy running-config startup-config
```

**A.15 Why would you test End-to-End Connectivity and what command would you use to test it?**

You would test end-to-end connectivity to verify that you are connected to the network. You would use the command ping (enter ip address)

### B. Reflection

**B.1 What is one thing that you learned from module 2?**

I learned the difference between console, ssh, and telnet and why you should only use telnet in a lab environment.

**B.2 What do you think the most important thing from this module was?**

I think properly making a password is the most important thing from this module.

### CLI Shortcut Reference

![Console shortcut reference table on a plain background, with columns Keystroke and Description. It lists: Tab — Completes a partial command name entry; Backspace — Erases the character to the left of the cursor; Ctrl+D — Erases the character at the cursor; Ctrl+K — Erases all characters from the cursor to the end of the command line; Esc D — Erases all characters from the cursor to the end of the word; Ctrl+U or Ctrl+X — Erases all characters from the cursor back to the beginning of the command line; Ctrl+W — Erases the word to the left of the cursor; Ctrl+A — Moves the cursor to the beginning of the line; Left Arrow or Ctrl+B — Moves the cursor one character to the left; Esc B — Moves the cursor back one word to the left; Esc F — Moves the cursor forward one word to the right; Right Arrow or Ctrl+F — Moves the cursor one character to the right; Ctrl+E — Moves the cursor to the end of command line; Up Arrow or Ctrl+P — Recalls the previous command in the history buffer, beginning with the most recent command; Down Arrow or Ctrl+N — Goes to the next line in the history buffer; Ctrl+R or Ctrl+I or Ctrl+L — Redisplays the system prompt and command line after a console message is received.](images/Hot%20Keys.png)

![Cisco IOS command reference page on a plain light background. A note explains that the Delete key is not recognized by the IOS command structure. The first table describes controls at the --More-- prompt: Enter Key displays the next line; Space Bar displays the next screen; any other key ends the display and returns to the previous prompt, except y, which answers yes and acts like Space Bar. A sentence introduces commands for exiting an operation. The second table says Ctrl-C ends configuration mode and returns to privileged EXEC mode, or aborts setup to the command prompt; Ctrl-Z ends configuration mode and returns to privileged EXEC mode; Ctrl-Shift-6 is an all-purpose break sequence for aborting DNS lookups, traceroutes, pings, and similar operations. The page has a clear, instructional tone.](images/Hot%20Keys%202.png)

### Presentation Slides

<details>
<summary>Show slides</summary>

![Module 2 slide 1, Agenda, with a dark background, a list of networking topics on the left, and a scenic aurora photograph on the right.](Slides/Module%202/Slide%201.png)

![Module 2 slide 2, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%202.png)

![Module 2 slide 3, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%203.png)

![Module 2 slide 4, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%204.png)

![Module 2 slide 5, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%205.png)

![Module 2 slide 6, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%206.png)

![Module 2 slide 7, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%207.png)

![Module 2 slide 8, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%208.png)

![Module 2 slide 9, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%209.png)

![Module 2 slide 10, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2010.png)

![Module 2 slide 11, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2011.png)

![Module 2 slide 12, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2012.png)

![Module 2 slide 13, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2013.png)

![Module 2 slide 14, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2014.png)

![Module 2 slide 15, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2015.png)

![Module 2 slide 16, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2016.png)

![Module 2 slide 17, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2017.png)

![Module 2 slide 18, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2018.png)

![Module 2 slide 19, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2019.png)

![Module 2 slide 20, a networking lesson screen with instructional text and visual content on a light background.](Slides/Module%202/Slide%2020.png)

</details>

### Configure Initial Switch Settings

#### Objectives

- Part 1: Verify the Default Switch Configuration
- Part 2: Configure a Basic Switch Configuration
- Part 3: Configure a MOTD Banner
- Part 4: Save Configuration Files to NVRAM
- Part 5: Configure S2

#### Background / Scenario

In this activity, you will perform basic switch configuration tasks. You will secure access to the command-line interface (CLI) and console ports using encrypted and plain text passwords. You will also learn how to configure messages for users logging into the switch. These message banners are also used to warn unauthorized users that access is prohibited.

Note: In Packet Tracer, the Catalyst 2960 switch uses IOS version 12.2 by default. If required, the IOS version can be updated from a file server in the Packet Tracer topology. The switch can then be configured to boot to IOS version 15.0, if that version is required.

#### Instructions

##### Part 1: Verify the Default Switch Configuration

###### Step 1: Enter privileged EXEC mode.

You can access all switch commands from privileged EXEC mode. However, because many of the privileged commands configure operating parameters, privileged access should be password-protected to prevent unauthorized use.

The privileged EXEC command set includes the commands available in user EXEC mode, many additional commands, and the configure command through which access to the configuration modes is gained.

1. Click S1 and then the CLI tab. Press Enter.
2. Enter privileged EXEC mode by entering the enable command:

Open Configuration Window for S1

```text
Switch> enable
Switch#
```

Notice that the prompt changed to reflect privileged EXEC mode.

###### Step 2: Examine the current switch configuration.

Enter the show running-config command.

```text
Switch# show running-config
```

Answer the following questions:

How many Fast Ethernet interfaces does the switch have?

How many Gigabit Ethernet interfaces does the switch have?

What is the range of values shown for the vty lines?

Which command will display the current contents of non-volatile random-access memory (NVRAM)?

Why does the switch respond with “startup-config is not present?”

##### Part 2: Create a Basic Switch Configuration

###### Step 1: Assign a name to a switch.

To configure parameters on a switch, you may be required to move between various configuration modes. Notice how the prompt changes as you navigate through the switch.

```text
Switch# configure terminal
Switch(config)# hostname S1
S1(config)# exit
S1#
```

###### Step 2: Secure access to the console line.

To secure access to the console line, access config-line mode and set the console password to letmein.

```text
S1# configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
S1(config)# line console 0
S1(config-line)# password letmein
S1(config-line)# login
S1(config-line)# exit
S1(config)# exit
%SYS-5-CONFIG_I: Configured from console by console
S1#
```

**Question**

Why is the login command required?

###### Step 3: Verify that console access is secured.

Exit privileged mode to verify that the console port password is in effect.

```text
S1# exit
Switch con0 is now available
Press RETURN to get started.
User Access Verification
Password:
S1>
```

Note: If the switch did not prompt you for a password, then you did not configure the login parameter in Step 2.

###### Step 4: Secure privileged mode access.

Set the enable password to c1$c0. This password protects access to privileged mode.

Note: The 0 in c1$c0 is a zero, not a capital O. This password will not grade as correct until after you encrypt it in Step 8.

```text
S1> enable
S1# configure terminal
S1(config)# enable password c1$c0
S1(config)# exit
%SYS-5-CONFIG_I: Configured from console by console
S1#
```

###### Step 5: Verify that privileged mode access is secure.

1. Enter the exit command again to log out of the switch.
2. Press **Enter** and you will now be asked for a password:

```text
User Access Verification
Password:
```

3. The first password is the console password you configured for line con 0. Enter this password to return to user EXEC mode.
4. Enter the command to access privileged mode.
5. Enter the second password you configured to protect privileged EXEC mode.
6. Verify your configuration by examining the contents of the running-configuration file:

```text
S1# show running-config
```

Notice that the console and enable passwords are both in plain text. This could pose a security risk if someone is looking over your shoulder or obtains access to config files stored in a backup location.

###### Step 6: Configure an encrypted password to secure access to privileged mode.

The enable password should be replaced with the newer encrypted secret password using the enable secret command. Set the enable secret password to itsasecret.

```text
S1# config t
S1(config)# enable secret itsasecret
S1(config)# exit
S1#
```

Note: The enable secret password overrides the enable password. If both are configured on the switch, you must enter the enable secret password to enter privileged EXEC mode.

###### Step 7: Verify that the enable secret password is added to the configuration file.

Enter the show running-config command again to verify the new enable secret password is configured.

Note: You can abbreviate show running-config as

```text
S1# show run
```

**Questions**

What is displayed for the enable secret password?

Why is the enable secret password displayed differently from what we configured?

###### Step 8: Encrypt the enable and console passwords.

As you noticed in Step 7, the enable secret password was encrypted, but the enable and console passwords were still in plain text. We will now encrypt these plain text passwords using the service password-encryption command.

```text
S1# config t
S1(config)# service password-encryption
S1(config)# exit
```

**Question**

If you configure any more passwords on the switch, will they be displayed in the configuration file as plain text or in encrypted form? Explain.

##### Part 3: Configure a MOTD Banner

###### Step 1: Configure a message of the day (MOTD) banner.

The Cisco IOS command set includes a feature that allows you to configure messages that anyone logging onto the switch sees. These messages are called message of the day, or MOTD banners. Enclose the banner text in quotations or use a delimiter different from any character appearing in the MOTD string.

```text
S1# config t
S1(config)# banner motd "This is a secure system. Authorized Access Only!"
S1(config)# exit
%SYS-5-CONFIG_I: Configured from console by console
S1#
```

**Questions**

When will this banner be displayed?

Why should every switch have a MOTD banner?

##### Part 4: Save and Verify Configuration Files to NVRAM

###### Step 1: Verify that the configuration is accurate using the show run command.

Save the configuration file. You have completed the basic configuration of the switch. Now back up the running configuration file to NVRAM to ensure that the changes made are not lost if the system is rebooted or loses power.

```text
S1# copy running-config startup-config
Destination filename [startup-config]?[Enter]
Building configuration...
[OK]
```

Close Configuration Window for S1

**Questions**

What is the shortest, abbreviated version of the copy running-config startup-config command?

Examine the startup configuration file.

Which command will display the contents of NVRAM?

Are all the changes that were entered recorded in the file?

##### Part 5: Configure S2

You have completed the configuration on S1. You will now configure S2. If you cannot remember the commands, refer to Parts 1 to 4 for assistance.

Configure S2 with the following parameters:

Open Configuration Window for S2

1. Device name: S2
2. Protect access to the console using the letmein password.
3. Configure an enable password of c1$c0 and an enable secret password of itsasecret.
4. Configure an appropriate message to those logging into the switch.
5. Encrypt all plain text passwords.
6. Ensure that the configuration is correct.
7. Save the configuration file to avoid loss if the switch is powered down.

[Back to all modules](Cisco-1-Notes.md)
