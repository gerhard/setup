After setting up a new Mac with development tools, apps, and configuring it for
the Nth time, I was determined to automate the process.  I've looked at
[sprout-wrap](https://github.com/pivotal-sprout/sprout-wrap),
[osxc](https://osxc.github.io/) &amp; [boxen](https://boxen.github.com/), but
the associated complexity was off-putting. There had to be a simpler way.

## Why?

I want an identical setup on any Mac with a single command.

I want a single command that updates an existing Mac configuration. brew update
&amp; upgrade are not enough. There's system software updates, vim plugin
updates &amp; brew cleanup.

I want to easily add a new brew formula, system font, go package or OS X app.
Creating a new file with a relevant name should be enough.

I want a lean &amp; fast vim environment. Having used vim janus for many years,
I want a vim with just the add-ons that I actually use.

I want a back-to-basics shell environment. oh-my-zsh is great, as is bash-it,
but I choose simplicity.

## How?

```sh
# Install Xcode Command Line Tools
xcode-select --install
# Clone this repository
git clone https://github.com/gerhard/setup.git ~/.setup
# Remove the homebrew casks, formulae etc. which you don't want, e.g.
# rm ~/.setup/homebrew/casks/{alfred,istat-menus}
# Run the setup (optionally, set a new name for your Mac)
~/.setup/setup my-new-mac
# Restart the Mac so that all system settings are applied correctly
# Re-run the setup to pick up any updates
~/.setup/setup
```

During the setup, you will be asked for your password as some terminal commands
require administrator privileges. Run `grep -r sudo ~/.setup` to find exactly
which ones.

Depending on the time that the `setup` command will take to run, you might need
to enter this password multiple times. Not ideal, but automating this didn't
feel right. I would rather enter my password multiple times than give a script
extended admin privileges.

Once the `setup` command completes, restart the Mac so that all system settings
can be applied correctly, then run the `setup` command again to ensure that the
system software is up to date. You will want to run this command periodically
as it will keep both the system software &amp; configuration updated.

I've kept the setup scripts minimal on purpose. There are extra setup steps
which are best done manually. Some were not worth automating, others were just
impossible. See the
[checklist.md](https://github.com/gerhard/setup/blob/master/checklist.md) for
all the steps which I still do manually on every new setup. As they are in
[Github task
list](https://github.com/blog/1375%0A-task-lists-in-gfm-issues-pulls-comments)
format, they are perfectly suited for Issues. [These are the Macs which I've
setup so far using this checklist
template](https://github.com/gerhard/setup/issues?q=is%3Aissue+is%3Aclosed).
