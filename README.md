# linux-plex-traffic-shaper 
This is a script for traffic shaping **egress** network traffic **from** a linux based [plex media server](https://plex.tv/) to other devices.  As of 2016-06-09, plex media server does not provide a way for you to limit traffic being served from your plex server to clients.  On a local network this is usually not a problem, however if you are using an asymmetric home internet connection, one or two external clients can [easily saturate your network connection, causing countless issues](https://twitter.com/cs_marshall/status/740943075288055808).

This repo contains a tracked copy of the original script by [rodalphoid](https://forums.plex.tv/profile/rodalphoid) from the Plex Media server Community forums [in this thread](https://forums.plex.tv/discussion/39823/howto-limit-plex-media-server-bandwidth-on-linux/), as well as the OS specific init files.

##Notes
* The script runs once and sets the tc and iptables rules, then exits, there is no persistent daemon.
* Ensure that the sch_htb module is available.
* For very high rates, you may need to adjust the [quantum values](http://mailman.ds9a.nl/pipermail/lartc/2003q1/007508.html)

##TBD:
* Init scripts for other distros (preferably as many as possible)
* "Stop" functionality for script, such that all TC and relevant iptables rules are removed, but not impacting the rest of the server's function
* General configuration notes
* FAQ 

##References:
* http://www.cyberciti.biz/faq/linux-traffic-shaping-using-tc-to-control-http-traffic
* https://forums.plex.tv/topic/39823-howto-limit-plex-media-server-bandwidth-on-linux/?p=466013
* http://serverfault.com/questions/174010/limit-network-bandwith-for-an-ip
 http://luxik.cdi.cz/~devik/qos/htb/manual/userg.htm