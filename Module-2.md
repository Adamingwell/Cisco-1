# Module 2: Basic Switch and End-Device Configurations

[All modules](Startup.md) · [Module 1](Module-1.md) · [Module 2](Module-2.md) · [Module 3](Module-3.md)

[Review questions](#review-questions) · [Full study guide](Class-Documents/Module-2-Switch-and-End-Device-Study-Guide.md) · [CLI shortcuts](#cli-shortcut-reference) · [Configure switch access and security](Packet-Tracer/Configure-Switch-Access-and-Security.md) · [Slides](#presentation-slides)

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

[Back to all modules](Startup.md)
