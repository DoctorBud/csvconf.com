# CSVConf.com

A static site, [http://csvconf.com/](http://csvconf.com).

Forked from [martini](https://github.com/codegangsta/martini) gh-pages branch.

## Develop

This is a [Jekyll](https://github.com/jekyll/jekyll) site!

Requirements:

To work on the CSVConf site locally, you'll first need to have the following installed:

- [Ruby 2.7](https://www.ruby-lang.org/en/)
- [Bundler](http://bundler.io/)

Once that's taken care of, here are the steps necessary to get it running locally:

1. clone this repository and `cd` into the `csvconf.com` directory
1. run the `bundle` command
1. run `bundle exec jekyll serve -w`

If everything worked, you should now have a local server running at http://localhost:4000. The `w` flag means the server will watch for changes and rebuild, so you can edit the site as needed and see the updated version in your browser right away.

## Installation notes

The current site is only compatible with Ruby 2.7.4, which is the current version supported by [GitHub Pages](https://pages.github.com). See [GitHub Pages Dependency versions](https://pages.github.com/versions/) for details.

### Ubuntu Installation

Using `apt` on Ubuntu 22.04 will install Ruby 3.0; to install a previous version you can use the following instructions:

```bash
# Install rbenv in your home directory
$ git clone https://github.com/rbenv/rbenv.git ~/.rbenv

# Add it to your PATH variable
$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
$ echo 'eval "$(rbenv init -)"' >> ~/.bashrc
$ exec $SHELL

# Install ruby-build plugin
$ git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build

# Install Ruby 2.7
$ rbenv install 2.7.1
$ rbenv global 2.7.1

# Check the correct install
$ ruby -v

# Install bundler
$ gem install bundler
$ rbenv rehash

```

### MacOS Installation

The default Ruby version for most modern MacOS versions is 3.x, which is incompatible with the version 2.7.x needed by GitHub Pages. There are a few ways to install Ruby 2.7.x on MacOS. The `rbenv` instructions for Ubuntu (see [Ubuntu Installation](#ubuntu-installation) above) can potentially be adapted for MacOS. If that does not work (see [Apple Intel macOS Ventura 13.1(M1): unable to install ruby 2.7.7, 3.1.3, 3.2.0, 3.0.5](https://github.com/rbenv/ruby-build/discussions/2127), the following Homebrew-based instructions may be used.

#### Ruby 2.7.x via Homebrew

If you have [Homebrew](https://brew.sh) installed on MacOS, the following command will install the latest 2.7.x version of Ruby:

```bash
brew install ruby@2.7
```

In order to override the default `ruby` installation on MacOS, it is necessary to adjust your shell's `PATH` environment variable prior to running any Ruby-related commands such as `bundle`, `ruby`, `gem`. While this `PATH` adjustment may be placed in your shell's initialization script (e.g., `~/.bashrc`), that will *globally* affect which `ruby` version is used, which may affect other tools and scripts unrelated to Jekyll. An alternative is to create a small script in your Jekyll directory (e.g., `rubyConfig.sh`) with the following contents:

```bash
export PATH="/usr/local/opt/ruby@2.7/bin:$PATH"
```

and then, prior to executing your Jekyll commands, remember to *source* the above script:

```bash
source rubyConfig.sh
```

## License

[MIT](LICENSE)
