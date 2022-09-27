# Practice Haml

Practice [Haml](https://haml.info/).

- Environment

```bash
$ rbenv -v
rbenv 1.2.0
$ rbenv version
2.7.6 (set by /Users/Neo/.rbenv/version)

$ type ruby
ruby is hashed (/Users/Neo/.rbenv/shims/ruby)
$ ruby -v
ruby 2.7.6p219 (2022-04-12 revision c9c2245c0a) [x86_64-darwin21]

$ type gem
gem is hashed (/Users/Neo/.rbenv/shims/gem)
$ gem -v
3.1.6

$ type bundle
bundle is hashed (/Users/Neo/.rbenv/shims/bundle)
$ bundle -v
Bundler version 2.1.4

$ type rake
rake is hashed (/Users/Neo/.rbenv/shims/rake)
$ rake -V
rake, version 13.0.1
```

- Setup Project

```bash
$ bundle init

$ cat ./Gemfile
# frozen_string_literal: true
source "https://rubygems.org"
git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }
# gem "rails"

$ gem search haml
haml (6.0.1 ruby java)

# Install Haml (Add To Gemfile And Run `bundle install`)
$ bundle add haml --version=6.0.1

$ cat ./Gemfile
# frozen_string_literal: true
source "https://rubygems.org"
git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }
# gem "rails"
gem "haml", "= 6.0.1"

$ cat ./Gemfile.lock
```

- Path Flag Is  Deprecated

```bash
$ bundle install --path ./vendor/bundle
[DEPRECATED] The `--path` flag is deprecated because it relies on being remembered across bundler invocations, which bundler will no longer do in future versions. Instead please use `bundle config set path './vendor/bundle'`, and stop using this flag

$ cat ./.bundle/config 
---
BUNDLE_PATH: "./vendor/bundle"

$ ls ./vendor/bundle/

# Reset
$ rm -rf ./.bundle/ ./vendor/

# Still Available Haml
$ bundle info haml
  * haml (6.0.1)
        Summary: An elegant, structured (X)HTML/XML templating engine.
        Homepage: https://haml.info
        Path: /Users/Neo/.rbenv/versions/2.7.6/lib/ruby/gems/2.7.0/gems/haml-6.0.1

$ bundle exec haml version
6.0.1
```

- Build (WIP)

```bash
$ bundle exec haml render ./src/index.haml
$ mkdir ./dist/
$ bundle exec haml render ./src/index.haml > ./dist/index.html
```


## Links

- [Neo's World](https://neos21.net/)
