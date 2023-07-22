# BUPDATE
## About
Bupdate is a collection of scripts for automatically updating the Willset rulesets.

As always, playing on williserver does not require the rulesets as they are stored on the server-side; however, having the rulesets up-to-date on your machine ensures that you can easily experiment with new changes outside of official games.

Currently I've completed scripts for Linux environments, but I plan to imminently release a Windows batch version. 

### Implementation 

Bupdate is two very simple scripts. 

`bgrab` clones/pulls the WillsetS and WillsetMelee git repos.

`bupdate` copies the relevant files (ruleset folders and .serv files) to the Freeciv data directory (i.e. /usr/share/games/freeciv). 

Since the copying script writes outside of the user's home directory, it must be run as root. 

The ruleset repositories will be cloned in the directory you ran the script. In order to prevent accidentally clogging your home directory with Willset repos, the scripts will not function if they aren't run from a directory named "bupdate". 

Note that bupdate works by copying files to the standard Freeciv data directory (i.e. /usr/share/games/freeciv). If you have a non-standard install location, edit the bupdate script's $install variable at the top of the script to reflect your install path. 

## Dependencies:
 - Git
 - Freeciv installed and in standard location.
 - Shell (uses bash by default.)

## Installation:

#### 1.  Install dependencies
All dependencies are probably installed on your system. If not, find a way to get them installed.

#### 2.  Get bupdate
First, find a place to put bupdate. 

Then, execute `git clone git@github.com:Beeciv/bupdate.git`. This will create a new directory for the bupdate scripts. Note that this is also where the rulesets will be stored/updated before being copied.

#### 3. Mark as executable
Execute `chmod +x bupdate` and `chmod +x bgrab`.

## Usage:
`./bgrab`

Then, `sudo ./bupdate`.
