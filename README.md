# Networking Project
<b>Objective -</b> Build a SIEM with network monitoring using Wazuh &amp; Suricata.

<!---------------------------------------------------------------------- SECTION BREAK ---------------------------------------------------------------------->

<h1>Network Monitoring with Wazuh and Suricata</h1>
	
<h2>Install Suricata</h2>
	
- <b>1. Setup to install the latest stable Suricata:</b>
  - `sudo apt-get install software-properties-common`
  - `sudo add-apt-repository ppa:oisf/suricata-stable`
  - `sudo apt-get update`
	
- <b>2. Then, you can install the latest stable with:</b>
  - `sudo apt-get install suricata`
 
<!-------------------------------------- SMALL BREAK -------------------------------------->

<h2>Configure Suricata</h2>
	
- 3. Then get the HOME_NET address from terminal paste:
  - `ip a s`
	
- <b>4. Copy "inet"</b>
	
- <b>5. Open suricata configuration file</b>
  - `sudo code /etc/suricata/suricata.yaml`
  - <i>(Note) "code" can be replaced with your own editor like "vi" for vim or "nano" for nano. Code opens VS Code if you have it downloaded.</i>
	
- <b>6. Paste "inet into HOME_NET address</b>
	
- <b>7. Find "af-packet" and make sure of correct interface:</b>
  - <i>(Note) To do this, usually you can type "ctrl + w" and then type in "af-packet".</i>
	
- <b>8. Then look at interface and where it may say "eth0" by default, make sure it is correct by going into terminal and typing "ifconfig" and it should be the first word after that.</b>
  - <i>(Note) EX: enp0s3</i>
	
- <b>9. Scrolls down to pcap and paste in the same interface</b>
	
- <b>10. Find (ctrl + w) "community-id" and change value from "false" to "true"</b>
	
- <b>11. Save and quit the configuration file.</b>

<!-------------------------------------- SMALL BREAK -------------------------------------->

	Add extra rules to Suricata to detect threats
	
	
	12. See what is available
		sudo suricata-update list-sources
		(Note) Some are paid
		
	13. To enable
		sudo suricata-update enable-source et/open
		(Note) Replace "et/open" with the ruleset you want.
	
	14. Then update the rulesets
		sudo suricata-update
		(Note) May get warnings about protocols that weren't configured and set to enable.
Will find those settings in the config file where you can enable or disable them yourself.

<!-------------------------------------- SMALL BREAK -------------------------------------->


