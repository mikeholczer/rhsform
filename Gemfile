source "https://rubygems.org"

gem "jekyll", "~> 4.4"

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.17"
  gem "jekyll-seo-tag", "~> 2.8"
  gem "jekyll-sitemap", "~> 1.4"
end

# Windows and JRuby do not include zoneinfo files, so bundle the tzinfo-data gem.
platforms :windows, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Lock `http_parser.rb` gem to `v0.6.x` on JRuby builds.
gem "http_parser.rb", "~> 0.6.0", platforms: [:jruby]

# Needed by Jekyll 4 to serve locally on Ruby 3.x.
gem "webrick", "~> 1.8"
