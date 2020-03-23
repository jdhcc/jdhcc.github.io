source "https://rubygems.org"

require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)
gem 'github-pages', versions['github-pages'], group: :jekyll_plugins
gem "builder", "~> 3.0"
gem "rdoc", "~> 6.0"
gem "rake", "~> 12.0"
gem "minitest", "~> 5.0"
gem "simplecov", "~> 0"
gem "rubocop", "~> 0.74.0"
gem "jekyll"
gem "jekyll-paginate"