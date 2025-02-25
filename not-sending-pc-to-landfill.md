## So, you wanna scrap my PC?

My desktop, well, under desktop, PC is admitedly quite old at 12 years (possibly more) 
but it runs Windows 10 just fine and does what I need it to do without too much trouble.
It is equipped with;
- Intel(R) Core(TM) i5-2400 CPU @ 3.10GHz
- 8GB RAM
- Samsung 850EVO 500GB SSD for the OS disk
- 4TB HDD 5inch for data storage (videos, music)
- 1TB HDD 5inch for applications and development
- 500GB HDD 2.5inch for temp data storage (music)
- BluRay Writer
- 8GB Ram
- multiple USBs ports hosting various HDDs
- memory card reader
- Nvidia GeForce GT430 graphics card (rarely used as I remote desktop to the box)
- Windows 10 Pro

Out of curiosity I researched a replacement on Amazon.be but found that most
systems on offer came in small boxes, ie. nowhere to put the HDDs and BluRay.
I don't want a gaming machine with all the silly flashing lights.
I do want something very quiet or at least no noisier than the existing box.
Many of the boxes on offer claimed to have Windows 11 installed but somewhat 
suspiciously had DP video ports instead of HDMI, seemd to have older chipsets,
were in the wrong language and possibly did not actually meet the Windows 11 requirements. 
This seemed to be backed up by some of the review comments. By the time I found boxes matching
my requirements the price had started to be way over what I want to pay
to replace my perfectly functioning system. Amazon.be did not appear to have
much of an offering for do-it-yourself assembly of a system and I would need to 
do much more research to figure out is needed for a self-assembly.

SO! I decided that it was plenty worth while trying one of the workaround methods to
put Windows 11 on my apparently obsolete and useless box.

As I was already familiar with Rufus I decided to go that route.

Download of the installation ISO was no problem - ahhh, the good old days when it
would take most of the day to download. It actually took longer to write the ISO to
the USB thumb drive than it did to download it!

I chose to simply run the 'setup.exe' on the thumb drive from the existing Windows 10
installation. 

The installation started, asked a few questions and then started installing. This is
a slow process so went for a round of golf. On my return I was greeted to a message 
about installing from the bootable USB drive or continuing. I selected to continue, things
proceeded and some while later I was back at my Windows 10 desktop. Something about failure in
the SafeOS boot phase and a meaningless error code. Googled for the code but the suggested meaning
was lack of storage space - that is one problem this system does not have!

Decided to give it another try. This time I stayed in the room with it until it got to the
stage where it was about to reboot. I yanked the USB drive just as it rebooted... the reboot
was successful and an 'installing updates' twirly circle appeared. More time passed, I had supper,
I returned to the system and lo! my PC looks like a Mac (ugggh!). 

Yippee! It seems I have successfully installed Windows 11 on my piece of scrap computer!

I've notice a few strange things since the installation:
- after an upgrade reboot the system did not automatically login anymore. I applied the old fix
  for this and was happy to find that it was still valid and appears to still work OK.
- the 4TB HDD kept on disconnecting and reconnecting while I was trying to copy a large file
  from it to the SSD. Couldn't figure out why this was happening. In the end I ran chkdsk. Since
  running chkdsk I have not noticed the problem anymore. I also switch the 4TB disk to use a
  6GB SATA port, moving the 1Tb disk to a 3GB SATA port. Both disks seem to be happy where they are now.
  I don't think this problem is directly related to Windows 11 as I have noticed some weird refreshing
  of the disk list in Explorer under Windows 10, but this was the first time I had seen actual errors
  while transferring files.

So that's it for now. 

I'll let it run for a few weeks before I contemplate repeating the excerise on the fanless computer. This
one gave alot of problems when it was upgraded from Windows 7, or was it just a Win10 upgrade, so I 
anticipate more issues than for the desktop machine.
  
