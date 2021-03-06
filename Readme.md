# Pomo ![Pomo](http://rstacruz.github.io/pomo.js/tomato-small.png)

```
$ npm install -g pomo
$ pomojs --help
```

![Screenshot](http://rstacruz.github.io/pomo.js/screenshot.png)

[![Build Status](https://travis-ci.org/rstacruz/pomo.js.png?branch=master)](https://travis-ci.org/rstacruz/pomo.js) [![NPM version](https://badge.fury.io/js/pomo.png)](http://badge.fury.io/js/pomo)

### Get started

``` sh
$ pomojs                              # Start a timer
$ pomojs "Conquer the world"          # Reason (great if you're logging)
$ pomojs -w 30                        # --work for 30 minutes
$ pomojs -b 12                        # --break for 12 minutes
$ pomojs --help
```

### Features

 * ridiculously simple (just type `pomojs`)
 * configurable work and break durations (`pomojs --work 10 --break 2`)
 * announces via text-to-speech ("5 minutes to go!")
 * notifications
 * no support for long breaks (this is a feature. problem?)
 * tmux support (status bar integration, shown above)
 * optional logging

### Requirements

 * node.js (required)
 * osx 10.8+: `gem install terminal-notifier`
 * linux: `sudo apt-get install libnotify-bin`
 * osx (others): [growlnotify]
 * linux: `sudo apt-get install espeak`

see [growl] readme for growl requirements.

----

### Tips

#### Tmux integration

Just add this to `~.tmux.conf`: (works almost exactly like in [pomo.rb][pomo-tmux])

     set-option -g status-right '#(cat ~/.pomo_stat)'

...then invoke it with `pomojs -t`.

#### Logging

Invoke it with `pomojs -l ~/.pomo.log` to log any pomodoros. Log file looks like 
this:

``` ini
[2013-06-17 mon]
6:14am - 6:44am = work on things (25m + 5m)
7:05am - 7:32am = do great stuff (25m + 2m, stopped)

[2013-06-18 tue]
6:14am - 6:44am = eat pizza (25m + 5m)
```

#### Saving your settings

Add this to your shell config, so that the next time you can invoke `pomojs` 
with preset settings:

``` sh
# ~/.bash_profile
alias pomo="pomojs --log ~/.pomo.log --tmux"
```

Even add more presets:

``` sh
# long-break pomodoro
alias longpomo="pomo -b 20"

# 10-minute pomodoro
alias minipomo="pomo -w 10"
```

#### Shortcut syntax

You can use this syntax to save some keystrokes.

``` sh
# pomojs <work> <break> <reason>
pomojs 25 2 Do things

# the same as:
pomojs --work 25 --break 2 Do things
```

-----

### Also see

 * [visionmedia/pomo] - pomodoro task manager (ruby gem)
 * [pmd] - has OSX status bar integration
 * [pom] - shell script

### Acknowledgements

Tomato icon by artbees. (via [iconfinder.net][icon])

(c) 2013, Rico Sta. Cruz. MIT

[visionmedia/pomo]: https://github.com/visionmedia/pomo
[pmd]: http://me.dt.in.th/page/pmd
[pom]: https://github.com/tobym/pom
[pomo-tmux]: https://github.com/visionmedia/pomo#tmux-status-bar-integration
[icon]: http://www.iconfinder.com/icondetails/56019/128/tomato_vegetable_icon
[growl]: https://npmjs.org/package/growl
[growlnotify]: http://growl.info/downloads
