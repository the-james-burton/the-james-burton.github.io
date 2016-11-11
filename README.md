This is my blog hosted at http://jimsey.org powered by [GitHub pages](https://help.github.com/articles/using-jekyll-with-pages/)

It based on [Daktilo](https://github.com/kronik3r/daktilo), a [Jekyll](http://jekyllrb.com) theme from [Motaquillah Maddane](https://github.com/kronik3r).

#### How to build and run locally (ubuntu 16.04)

```bash
sudo apt-get install ruby2.3 ruby2.3-dev
sudo apt-get install build-essential bison openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libxml2-dev autoconf libc6-dev ncurses-dev automake libtool
sudo gem install bundler
bundle install
bundle exec jekyll serve
```

The site is then available at http://localhost:4000
