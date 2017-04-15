# gpp-decrypt
gpp-decrypt

This tool was released by Chris Gates on Friday, October 19, 2012. It was imported here because a version controlled draft could not be located.

From Chris:

Group Policy Preferences and Getting Your Domain 0wned So i put this link out on twitter but forgot to put it on the blog.

I did a talk at the Oct 20012 NovaHackers meeting on exploiting 2008 Group Policy Preferences (GPP) and how they can be used to set local users and passwords via group policy.

I've run into this on a few tests where people are taking advantage of this exteremely handy feature to set passwords across the whole domain, and then allowing users or attackers the ability to decrypt these passwords and subsequently 0wning everything :-)

So here are the slides: Exploiting Group Policy Preferences from chrisgates

Blog post explaining the issue in detail: http://esec-pentest.sogeti.com/exploiting-windows-2008-group-policy-preferences

Metasploit post module: http://metasploit.com/modules/post/windows/gather/credentials/gpp

PowerShell module to do it: http://obscuresecurity.blogspot.com/2012/05/gpp-password-retrieval-with-powershell.html

I ended up writing some ruby to do it (the blog post has some python) because the metasploit module was downloading the xml file to loot but taking a poop prior to getting to the decode part. now you can do it yourself:
In Action:

user@ubuntu:~$ ruby gpp-decrypt-string.rb
Local*P4ssword!
