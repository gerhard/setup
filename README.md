After setting up a new Mac with development tools, apps and configuring it the
nth time, I was determined to automate the process.  I've looked at
[sprout-wrap](https://github.com/pivotal-sprout/sprout-wrap),
[osxc](https://osxc.github.io/), [boxen](https://boxen.github.com/) and others,
but the associated complexity was off-putting.  There had to be a simpler way.
Peel back all the layers in any of the above tools, and one will find calls to
terminal commands like `defaults`, `brew`, `go`, `ln`, `kill` etc.  Indirection
and abstractions are wonderful concepts, but knowing when not to use them is
possibly the most valuable skill.

## Why?

I want an identical setup on any Mac, in less than 30 minutes.

I want a single command that updates my entire Mac configuration. brew update
&amp; upgrade are not enough. There's system software updates, vim plugins
updates &amp; brew cleanup.

I want to easily add a new brew formula, system font, go package or OS X app.
Creating a file with the relevant name is all it takes.

I want a lean &amp; fast vim environment. Having used vim janus for many years,
I wanted a vim with just the add-ons that I actually use.

I want a back-to-basics shell environment. oh-my-zsh is great, as is bash-it,
but I choose simplicity.

## How?

### On a new Mac

1. Install Xcode Command Line Tools
```
xcode-select -p
```
1. Clone this repository
```
git clone https://github.com/gerhard/setup.git ~/setup
```
1. Remove the homebrew casks &amp; formulae which you don't want
1. Run the setup, optionally providing a new name for your Mac
```
~/setup/new [eve]
```
You will be asked for your password as some terminal commands require
administrator privileges. Run `grep -r sudo ~/setup` to find exactly which
ones. Depending on the time that the `new` command will take to run, you might
need to enter this password multiple times.

### Keep the setup updated

I promised a single command:
```
~/setup/update
```
