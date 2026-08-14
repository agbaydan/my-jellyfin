# Server

I am running my franken PC(mix of old parts) as a server. Previously I was running jellyfin on a raspberry pi 4B locally. That worked fine but no way could that thing handle multiple streams and hardware acceleration, meaning transcoding was up to the client which can be more limiting. 

Specs are:
* Intel Core i5-10600K 4.1 GHz 6-Core Processor
* G.Skill Ripjaws V 16 GB (2 x 8 GB) DDR4-2400 CL15 Memory 
* 1 TB 3.5" 7200RPM hard drive
* OS: fedora server 44

Storage needs upgrading. My PC case has 3x 3.5" and 2x 2.5" hard drive bays, so I am thinking of getting 3x 3.5" 8TB hard drives, and setting them up with RAID 5 configuration. Idk what to use for setting up RAID but this seems promising: https://docs.fedoraproject.org/en-US/fedora-server/installation/sw-raid-upon-installation/ although if I have to reinstall fedora server that would be slightly annoying.
