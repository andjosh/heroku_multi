heroku_multi
===

This is a simple shell script to run the same command on multiple [Heroku][0] applications at once. The command can be run on each app synchronously or on all asynchronously.

Use cases:
- You need to update the same environment variable on multiple apps at once.
- You want to restart or pause multiple apps.
- You want to get home early to play with the kids.

## Usage
~~~sh
$ heroku_multi <command> -a app [app] [app...] [--async]

# e.g. Set a config variable on three apps simultaneously
$ heroku_multi config:set FOO=bar -a app-one two-app three-apps --async

# Flags:
# -a            apps on which to invoke the command
# 
# --async       spawn a background shell for the command on each
#               app, executing asynchronously
~~~

## Installation
~~~sh
# requires heroku CLI from https://devcenter.heroku.com/articles/heroku-cli
$ curl -L https://raw.githubusercontent.com/andjosh/heroku_multi/master/heroku_multi -o ~/bin/heroku_multi && chmod +x ~/bin/heroku_multi
~~~

[0]: https://heroku.com
