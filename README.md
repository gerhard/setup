After setting up a new Mac with development tools, apps and configuring it the
nth time, I was determined to automate the process.

I've looked at [sprout-wrap](https://github.com/pivotal-sprout/sprout-wrap),
[osxc](https://osxc.github.io/), [boxen](https://boxen.github.com/) and others,
but the associated complexity was off-putting.  There had to be a simpler way.
Peel back all the layers in any of the above tools, and one will find calls to
commands like `defaults`, `brew`, `go`, `ln`, `kill` etc.  Indirection and
abstractions are wonderful, but just as everything, knowing when not to use
them is possibly the most valuable skill.

I wanted it to be easy to add/remove a new brew formula, go package or OS X
app.  I wanted to have my vim environment configured with just the features
that I use on a daily basis.  Having used vim janus for many years, I wanted
something leaner, faster & simpler.  I wanted a back-to-basics shell
environment.  I wanted a single command that updates my entire setup, or that
returns the Mac back to its defaults.

## Fresh Mac

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

## Regular updates

## Cleanup
