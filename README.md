# GUP

Upload gists from the command line.

## Installation

Drop the script somewhere in your path and make it excecutable. e.g.

    curl https://raw.githubusercontent.com/callum-oakley/gup/master/gup > ~/.local/bin/gup && chmod +x ~/.local/bin/gup

## Configuration

You'll need a [github personal access token][token] with the `gist` scope so
you can create gists. At its most basic, you can call `gup` like this, passing
a token explicitly:

    gup -t $GUP_TOKEN hello.txt

but you'll probably want to set a shell alias that fills in your token for you

    alias gup='gup -t $GUP_TOKEN'

so you can just

    gup hello.txt

## Usage

From `gup -h`:

    usage: gup [-h] [-s] [-d DESC] -t TOKEN FILE

    Upload files to https://gist.github.com/ and print the uploaded url to
    stdout.

    positional arguments:
      FILE                  file to upload

    optional arguments:
      -h, --help            show this help message and exit
      -s, --secret          create secret gist
      -d DESC, --description DESC
                            description for your gist
      -t TOKEN, --token TOKEN
                            github personal access token

## Tips

On a successful upload, `gup` prints the url of your gist to stdout. You might
want to pipe this straight to your clipboard with something like

    gup hello.txt | xsel

[token]: https://github.com/settings/tokens
