# BUPDATE  
## About  
Bupdate is a collection of scripts for automatically updating the Willset rulesets.  
  
As always, playing on williserver does not require the rulesets as they are stored on the server-side; however, having the rulesets up-to-date on your machine ensures that you can easily experiment with new changes outside of official games.  
  
### Implementation  
  
Bupdate is two very simple scripts.  
  
`bgrab` clones/pulls the WillsetS and WillsetMelee git repos.  
  
`bupdate` copies the relevant files (ruleset folders and .serv files) to the Freeciv data directories specified in the `installdirs` file.
  
The ruleset repositories will be cloned in the directory you ran the script. In order to prevent accidentally clogging your home directory with Willset repos, the scripts will not function if they aren't run from a directory named "bupdate".  
  
Note that you may need to run bupdate as `root` to copy files in locations you don't have access to.
  
## Dependencies:  
- Git  
- Freeciv installed and in standard location.  
- Shell (uses bash by default.)  
  
## Installation:  
  
#### 1. Install dependencies  
All dependencies are probably installed on your system. If not, find a way to get them installed.  
  
#### 2. Get bupdate  
First, find a place to put bupdate.  
  
Then, execute `git clone git@github.com:Beeciv/bupdate.git`. This will create a new directory for the bupdate scripts. Note that this is also where the rulesets will be stored/updated before being copied.  

#### 3. (optional) Specify targets.
Navigate to `installdirs` and edit the file to include all directories that you want to place the rulesets in.

NOTE: Each directory should be placed on a newline.

By default, rulesets are placed in `/usr/share/games/freeciv`

#### 4. Mark as executable  
Execute `chmod +x bupdate` and `chmod +x bgrab`.  
  
## Usage:  
`./bgrab`  
  
Then, `./bupdate` (or `sudo ./bupdate`)
