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

#### How to merge all the posts together into one file?

This script is a quick hack to convert many posts into a single post. It can be used to aggregate up everything into a one-page take away.

```bash
cd _posts
cat *aftdiw* > temp.md
rpl -e "subtitle:" "\n####" temp.md
rpl -e "title:" "#" temp.md
rpl -qe "categories: [photography]\n---" "" temp.md
rpl -q "layout: post" "" temp.md
head -6 2017-08-01-aftdiw-introduction.md > temp.header.txt
grep -v "date:   2017" temp.md > temp2.md
cat temp.header.txt temp2.md > 2017-08-31-aftdiw-one-page.md
rm temp.md temp2.md temp.header.txt
```

#### How to separate content from the post itself, for easier joining

The script above is helpful to aggregate content into one page if the author has not provided single page versions of series. The below is the 'right' way to separate markdown content from presentation when using Jekyll. This advice is based on [this comment](https://github.com/jekyll/jekyll/issues/1303#issuecomment-21067548)

0. Extract or author the markdown post content into it's own file and subdirectory in _includes. Just the content, not the metadata at the top.
0. Your original post will now just contain the metadata header. Add a bit of code below this metadata to include the content:
```
{% capture the_content %}{% include aftdiw/1-aftdiw-introduction.md %}{% endcapture %}
{{ the_content | markdownify }}
```
0. Make a new post for your 'one-pager' that has multiple entries of the above code for all the posts you want to combine.

Doing the above, makes for a very flexible content/presentation separation. As pure markdown, it should be easier to convert it into other formats as need be.
