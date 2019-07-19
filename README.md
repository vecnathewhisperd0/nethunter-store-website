# The NetHunter App Store Website

This is the repository for the website at <https://store.nethunter.com>.  It
is a slightly custimised version of [F-Droid](https://f-droid.org) based on Jekyll
and you can find the development version [here](https://staging.nethunter.com).

## Building

You need to have Jekyll 3.2+ installed what is easily done with Gem which depends on Ruby 2.0+.
Because of the F-Droid plugin you need to have zlib installed.

```
sudo apt-get install ruby-full build-essential zlib1g-dev
sudo gem install bundler
bundle install
```

To build the website, run:

```
bundle exec jekyll build
```

If you want to build the website and
serve it with a local server at [localhost:4000](http://localhost:4000),
use:

```
bundle exec jekyll serve
```


## License

This program is Free Software:
You can use, study share and improve it at your will.
Specifically you can redistribute and/or modify it under the terms of the
[GNU Affero General Public License](https://www.gnu.org/licenses/agpl.html)
as published by the Free Software Foundation,
either version 3 of the License,
or (at your option) any later version.
