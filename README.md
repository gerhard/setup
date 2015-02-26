After setting up a new Mac with development tools, apps and configuring it the
nth time, I was determined to automate the process.

I've looked at [sprout-wrap](https://github.com/pivotal-sprout/sprout-wrap),
[osxc](https://osxc.github.io/), [boxen](https://boxen.github.com/) and others,
but the associated complexity was off-putting.  There had to be a simpler way.
Peel back all the layers in any of the above tools, and one will find calls to
terminal commands like `defaults`, `brew`, `go`, `ln`, `kill` etc.  Indirection
and abstractions are wonderful concepts, but knowing when not to use them is
possibly the most valuable skill.

## Why?

I want to easily add/remove a new brew formula, go package or OS X app.

I want a stripped-down vim environment with just the add-ons that I rely on a
daily basis.  I have used vim janus for many years. I want something leaner,
faster & overall simpler.

I want a back-to-basics shell environment. oh-my-zsh is great, as is bash-it,
but I value simplicity over features.

I want a single command that updates my entire Mac configuration.

I want a single command that returns my Mac back to its defaults.

I want an identical setup on any Mac, in less than 30 minutes.

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
1. Remove the homebrew casks & formulae which you don't want
1. Run the setup, optionally providing a new name for your Mac
```
~/setup/new [eve]
```

You will be asked for your password, some.

### Keep the dependencies updated

### Restore the Mac back to its defaults
