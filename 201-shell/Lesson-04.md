# Shell 201
## Lesson 4: apt install, git clone, wget, curl

`cd ~/Work/Pinker/shell/201`

`gedit &`

`nautilus . &`
___

*Install git and curl*

`sudo apt install git curl`

*Download the entire verb.ink page using wget*

`wget -r http://verb.ink`

*Download the verb.ink index page using curl*

`curl http://verb.ink`

`ls`

*Note it only showed the html content, to save it specify an output file:*

`curl http://verb.ink > verb.ink.html`

`ls`

*Open it with Firefox*

`firefox verb.ink.html`

## Download the inkVerb/vrk repo from GitHub

### zip via wget

*Download Vrk using wget*

`wget https://github.com/inkVerb/vrk/archive/master.zip`

`ls`

*Specify an output file*

`wget -O vrk.zip https://github.com/inkVerb/vrk/archive/master.zip`

`ls`

*Clean up*

`rm master.zip`

### zip via curl

`curl https://github.com/inkVerb/vrk/archive/master.zip` (wrong)

*Note the redirect message; use* `-L` *to follow redirects*

`curl -L https://github.com/inkVerb/vrk/archive/master.zip` (wrong)

*Note it dumped the raw output to the terminal rather than saving it*

*Solution: Specify an output file*

`curl -L https://github.com/inkVerb/vrk/archive/master.zip > vkr-curl.zip`

`ls`

*Now that you get the point, we don't need it anymore*

`rm vkr-curl.zip`

### tarball via curl

*Substitute* `github.com` *for* `api.github.com/repos/` *& append with* `/tarball` *& include output file*

`curl -L https://api.github.com/repos/inkVerb/vrk/tarball > vrk.tar`

`ls`

*Untar it*

`tar xzf vrk.tar`

`ls`

*Note the strange new directory* `inkVerb-vrk-SOME_CRAZY_NUMBER`

*...that's it, delete it with:*

> `rm inkVerb-vrk-SOME_CRAZY_NUMBER`

*We don't need to keep that tarball either*

`rm vrk.tar`

### tarball via curl & untar (single command)

*Substitute* `github.com` *for* `api.github.com/repos/` *& append with* `/tarball` *& untar it right away*

`curl -L https://api.github.com/repos/inkVerb/vrk/tarball | tar xz`

`ls`

*Note the same strange directory* `inkVerb-vrk-SOME_CRAZY_NUMBER`

*...that's it, delete it with:*

> `rm inkVerb-vrk-SOME_CRAZY_NUMBER`

### repo via git clone

`git clone https://github.com/inkVerb/vrk`

`ls`

`rm -r vrk`

*Note the error message; you don't own it!*

`sudo rm -r vrk`

`ls`

#### [Lesson 5: tar, zip, gzip, bzip2, xz](https://github.com/inkVerb/pinker/blob/master/201-shell/Lesson-05.md)
