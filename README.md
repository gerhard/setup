Dotfiles are cool. A script that managed all those dotfiles is slightly better.
What about the brew formulae? OS X apps? The OS X configs?

I've looked at [sprout-wrap](https://github.com/pivotal-sprout/sprout-wrap),
[osxc](https://osxc.github.io/), [boxen](https://boxen.github.com/) and others,
but the associated complexity was off-putting, so I continued to do things
manually. After all, I only had to do this once a year - at most. After the
20th time though, I got fed up with it - there had to be a better way. I
partnered with my favourite scripting language, bash, and gave it a shot. There
are 3 scenarios that I'm accounting for:

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
