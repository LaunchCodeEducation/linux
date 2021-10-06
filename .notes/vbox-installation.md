# Download VirtualBox and setup on your OS

## Windows

- download the software
- run the .exe
- go through the setup steps
- start virtualbox

## MacOS

- download the software
- drag the .dmg to your applications folder
- start virtualbox

## Linux

- if you are using linux I assume you are handy enough with computers to figure this out on your own. For a relatively modern debian-based system it should be as simple as `sudo apt install virtualbox`

- for other distros checkout Virtualbox's installation page

# Download the .iso we will be using in this class (ubuntu 20.04) provide link (even better provide a place they can download it from LC)

# Create a new Virutal Machine

- from within virtual box clikc the `New` button

- give this machine a name (linux-intro)
- set the Machine Folder if desired
- Select Linux for Type
- Select Ubuntu (64-bit) for Version
- give it 2-4 GB of RAM
- create virtual disk VDI (deafult

## further configuration of VM

- go to settings of the machine you just created (we need to set the .iso it will use)
- go to storage
- click controller: IDE empty, click the CD/DVD icon and select the .iso you downloaded earlier (we are setting the image to be used when this Virtual Machine boots (w/o setting this the virtual machine although configured to be a part of your file system, having acess to your RAM, CPU, and remaining hardware will not have an OS!
- click OK
- then start the machine

## Installing Ubuntu to this virtual machine

- click install ubuntu (note this is installing ubuntu to the VDI you created earlier. It is not overwriting your OS)
- select English (US) or whateveer keyboard layout you want & click continue
- minimal installation (we don't need the office sofware, games, and media players because this isn't for an every day user, it's just for deploying our applications)
- download updates while installing ubuntu is fine & continue
- leave it on the default (as further proof that it's not detecting your actual OS look at the message it says (This computer currently has no detected operation systems. It would be able to detect your OS if it was looking at your entire harddrive, and not this virtual hard drive we created)
- leave it on erase disk and install ubuntu & click install now
- click continue on the pop up if you see one
- if it doesn't detect your timezone go ahead and select it & continue
- put in your name (this will fill out the next twwo boxes which you should just leave as default)
- set an easy to remember password (since this is a transient machine, you don't need a great password. I will be using `admin` & continue
- wait for it to installing and finish setup (this will take a hot minute)  
  - if you didn't select minimum installation you will have even more of a wait
  - it's going to take everyone a different amount of time to get through this step (based on amount of RAM and CPU you gave the machine, your internect throughput, differences in hardware, etc)
- after installation is complete the vm will need to restart, click rsetart now
- it will say please remove the installatio medium, then press enter we don't have one because we didn't boot from a CD or USB stick, so just click in the box and then hit enter on your keyboard
- (NOTE: depending on your computer mouse over may be a bit wonky, but virtualbox provides some information on making that better
- select your user account (paul) enter your password (admin) & enter
- some first time stuff will pop up, we dont' care about it, we aren't using this machine as a general purpose daily operating system, so we don't want to connect our online accounts, or install more software (exit, or skip out of these options, they should only pop up once)
- and you are in (I literally clicked next, like three times)

- what could you do from here?
  - literally anything you would do with a computer
    - try opening the web browser (firefox)
    - try opening the file explorer
    - try opening libreoffice (the document opener and creator)
  - it's a full operating system that you didn't have to pay for, and has some very cool things you can do with it. if you were so inclined you could use it as your everyday general purpose OS

- open a terminal


### Quality of Life

- change the display (search for display change it to something that fits your screen, or gets you some more real estate
- close (save machine state -- super slick, takes more time)
- close (shutdown the machine -- this is akin to shutting down your own machine
- you can start and stop your virtual machine to your hearts content



