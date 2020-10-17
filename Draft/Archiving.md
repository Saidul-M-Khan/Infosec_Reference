### A Guide to Archiving Websites
* From: https://gist.githubusercontent.com/mullnerz/9fff80593d6b442d5c1b/raw/2c511e82f998bc489d9e300870f8789c77c2b49b/archive-website.md
* "The command I use to archive a single website"
	* `sh wget -mpck --html-extension --user-agent="" -e robots=off --wait 1 -P . www.foo.com`
* **Explanation of the parameters used**
	* `-m` (Mirror) Turns on mirror-friendly settings like infinite recursion depth, timestamps, etc.
	* `-c` (Continue) Resumes a partially-downloaded transfer
	* `-p` (Page requisites) Downloads any page dependencies like images, style sheets, etc.
	* `-k` (Convert) After completing retrieval of all files…
		* converts all absolute links to other downloaded files into relative links 
		* converts all relative links to any files that weren’t downloaded into absolute, external links 
		* In a nutshell: makes your website archive work locally
	* `--html-extension` this adds .html after the downloaded filename, to make sure it plays nicely on whatever system you’re going to view the archive on
	* `–user-agent=””` - Sometimes websites use robots.txt to block certain agents like web crawlers (e.g. GoogleBot) and Wget. This tells Wget to send a blank user-agent, preventing identification. You could alternatively use a web browser’s user-agent and make it look like a web browser, but it probably doesn’t matter.
	* `-e robots=off` - Sometimes you’ll run into a site with a robots.txt that blocks everything. In these cases, this setting will tell Wget to ignore it. Like the user-agent, I usually leave this on for the sake of convenience.
	* `–wait 1` - Tells Wget to wait 1 second between each action. This will make it a bit less taxing on the servers.
	* `-P .` - set the download directory to something. I left it at the default “.” (which means “here”) but this is where you could pass in a directory path to tell wget to save the archived site. Handy, if you’re doing this on a regular basis (say, as a cron job or something…)
	* `http://url-to-site` - this is the full URL of the site to download. You’ll likely want to change this.
* **Sources**
	- [Archiving a (WordPress) website with wget | D’Arcy Norman dot net](http://darcynorman.net/2011/12/24/archiving-a-wordpress-website-with-wget/)
	- [Archiving a Website With Wget](http://www.dheinemann.com/2011/archiving-with-wget/)

```
